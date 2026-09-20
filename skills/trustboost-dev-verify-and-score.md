---
name: trustboost-dev-verify-and-score
description: Read a wallet's TrustBoost Score and trust tier, verify a Proof of Sanitization on Solana, and check an operator's privacy budget — the free, unauthenticated read side of the TrustBoost PII Sanitizer API.
api: openapi/trustboost-dev-openapi.json
operations:
  - health_check
  - get_trustboost_score
  - verify_proof
  - get_budget_status
method: generated
generated: '2026-09-19'
grounding: Every operationId above exists verbatim in openapi/trustboost-dev-openapi.json. Every response quoted was observed live on 2026-09-19 with the ids shown, or is quoted from the provider's own documents.
---

# Verify a TrustBoost proof and read a wallet's trust tier

All four operations are free, need no wallet, no payment and no header beyond `Accept: application/json`. None of them consumes TRIAL quota. Base URL `https://api.trustboost.dev` — the apex `trustboost.dev` does not resolve.

## 0. Is the service up?

`GET /health` (`health_check`). Observed:

```json
{"status":"ok","version":"2.6.0","service":"TrustBoost-PII-Sanitizer","infrastructure":"FastAPI+Supabase+Render"}
```

The provider's own instruction is fail-closed: if this is unreachable, do not fall back to passing unsanitized text to an LLM.

## 1. Read a wallet's TrustBoost Score

`GET /score/{wallet_address}` (`get_trustboost_score`). `wallet_address` is whatever string the caller used on `/sanitize` — a public Solana address or an agent id. Tiers are `NEW`, `ACTIVE`, `VERIFIED`, `TRUSTED`.

Observed for a wallet with no history (`/score/probe`):

```json
{"status":"success","wallet":"probe","trustboost_score":null,"trust_tier":"NEW",
 "message":"No sanitization history found for this wallet. Score will be available after first use.",
 "history":{"total_requests":0,"first_seen":null,"last_seen":null}}
```

A `null` score with tier `NEW` is a normal state, not an error. The score is an aggregate of that wallet's own sanitization history (PRIVACY.md v4.0), so it says how much a counterparty has used TrustBoost — nothing more.

## 2. Verify a Proof of Sanitization

`GET /verify/{anchor_tx}` (`verify_proof`). `anchor_tx` is the `data.proof_of_sanitization.solana_tx` returned by a **paid** `/sanitize` response. `/anchor/{anchor_tx}` is an undeclared alias.

- **200** — proof verified.
- **404** — no record. Observed for an unknown id:

```json
{"status":"not_found","message":"No sanitization record found for this Solana transaction",
 "anchor_tx":"probe","note":"Only paid sanitizations are anchored on Solana"}
```

TRIAL calls are never anchored, so a 404 on a TRIAL wallet's activity is expected. The provider also publishes the explorer form `https://solscan.io/tx/{anchor_tx}` in the agent card's `trust.proof_explorer`.

## 3. Check a privacy budget

`GET /budget/{operator_id}` (`get_budget_status`). Observed for an unregistered operator:

```json
{"status":"success","operator_id":"probe","budget_active":false,
 "message":"No privacy budget registered for this operator. Unlimited access."}
```

Budgets are operator-configured daily and per-context limits (PRIVACY.md: `daily_limit`, `context_limit`, `is_active`). No public operation registers one; only this read exists.

## Before paying for anything

The write path is out of scope for this skill; if you go on to it, call `GET /preflight` (undeclared in the contract, live 200) and store the hash from `GET /policy` first — the provider says to re-evaluate if the hash changes. Unused paid quota is stated to be non-refundable, with a 48-hour dispute window by email. See `conventions/trustboost-dev-conventions.yml` for the payment and idempotency rules and `errors/trustboost-dev-problem-types.yml` for the three error envelopes you may receive.
