---
name: flowhomes-eu-discover-then-pay
description: Find the right Qorevia tool for a need without spending, read its price and schema from the free 402 preflight, then pay exactly once via x402 and retry — the provider's documented call pattern.
api: flowhomes-eu:qorevia-market-intelligence-api
operations: [csv_profile, json_shape, jwt_decode, regex_test, evm_address_syntax, tick_pnl, ohlcv_state, risk_levels, strategy_grade, session_state]
routes: ['GET /api/find', 'POST /api/route', 'GET /api/catalog', 'GET /health']
method: generated
source: openapi/flowhomes-eu-openapi.json, https://api.flowhomes.eu/skill.md, https://api.flowhomes.eu/.well-known/x402, live 402 observed 2026-09-19
---

# Discover, preflight, pay once, retry

Qorevia has no API keys. Every paid route answers an unpaid request with HTTP 402 and a
`PAYMENT-REQUIRED` header; you pay in USDC on Base Mainnet (eip155:8453) through x402 v2 and
retry the identical request with `PAYMENT-SIGNATURE`. Discovery is free.

## Steps

1. **Find the tool — free.** `GET https://api.flowhomes.eu/api/find?q=<natural-language need>&limit=3`
   (or MCP tool `qorevia_find`, or an A2A `message/send`). The response's `matches[]` carries `key`,
   `method`, `path`, `priceUsd`, `network`, `inputSchema`, `exampleInput` and `outputExample`.
   Browse everything with `GET /api/catalog` (13 items, `offset`/`limit`).
2. **Check the price against your budget before calling.** Prices as of 2026-09-19 (manifest
   `/.well-known/x402`): csv_profile, json_shape, jwt_decode, ohlcv_state $0.0025; regex_test $0.0034;
   session_state, risk_levels $0.005; evm_address_syntax $0.01; strategy_grade $0.02; tick_pnl $0.05.
   The x402 requirement quotes the same amount in USDC base units (`"5000"` = $0.005).
3. **Preflight — still free.** Send the real request with no payment. Expect `402`, body `{}`, and
   decode the base64 `PAYMENT-REQUIRED` header: `accepts[0]` gives `amount`, `asset`
   (`0x8335…2913`, USDC on Base), `payTo` (`0x80cd…3382`) and `maxTimeoutSeconds` (300);
   `extensions.bazaar.schema` repeats the input schema. Verify `payTo` matches the manifest's
   `rails[0].payTo` before paying.
4. **Pay and retry within 300 seconds.** Use an x402 v2 client (the manifest names the facilitator
   `https://facilitator.payai.network`) to settle `amount` to `payTo`, then repeat the exact same
   request (same method, path, query and body) with the `PAYMENT-SIGNATURE` header. A `200` carries the
   result — an object with `additionalProperties: true` shaped like the operation's `example`.
5. **Attribute a referral if you have one.** Append `?ref=QF-XXXXXXXXXX` or send `X-Qorevia-Ref` on
   the paid call (Founders Network; does not change the price).

## Rules the docs do and do not state

- **Every retry is a new payment.** There is no Idempotency-Key and nothing says a replayed
  `PAYMENT-SIGNATURE` is honoured once. Do not auto-retry a paid call after a network error without
  checking whether the first settlement went through.
- **No refunds are published.** USDC settlement on Base is final and no dispute or credit path exists on
  any served surface. Spend only what the free preflight told you.
- **`503` means do not pay.** The spec declares "payment is not requested for MT5 routes during preflight
  failure"; a 503 arrives instead of a 402. For the three MetaTrader routes see the sibling skill.
- **Application errors on free routes come back as HTTP 200 with `ok: false`** (`reason: NO_MATCH`,
  `error: invalid_wallet`). Read the body.
- Errors: `errors/flowhomes-eu-problem-types.yml`. Conventions: `conventions/flowhomes-eu-conventions.yml`.
