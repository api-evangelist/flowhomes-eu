---
name: flowhomes-eu-xauusd-snapshot
description: Build a live gold (XAUUSD) market snapshot — quote, recent OHLCV bars and computed market state — from Qorevia's read-only MetaTrader 5 feed, checking terminal health first so no payment is made for a route that would 503.
api: flowhomes-eu:qorevia-market-intelligence-api
operations: [xau_quote, xau_bars, xau_market_state, session_state]
routes: ['GET /health']
method: generated
source: openapi/flowhomes-eu-openapi.json (parameters, enums, bounds and examples verified in the spec), https://api.flowhomes.eu/health observed 2026-09-19
---

# XAUUSD snapshot: health, quote, bars, market state

Three paid GET routes read a read-only MetaTrader 5 terminal ("Eightcap Global MT5 Terminal",
`tradeAllowed: false`). Total cost for one full snapshot: $0.01 + $0.02 + $0.03 = $0.06 in USDC,
plus $0.005 if you add the session clock. Payment follows the discover-then-pay skill.

## Steps

1. **Check the terminal before spending.** `GET https://api.flowhomes.eu/health` (free). Proceed only if
   `mt5.ok` and `mt5.connected` are `true`. When the terminal is down the paid routes return `503`
   *instead of* `402` — the spec says payment is not requested during preflight failure — so a `503`
   after this check is a race, not a charge.
2. **Quote — `xau_quote`.** `GET /api/xau/quote?symbol=XAUUSD` ($0.010). `symbol` is optional and
   defaults to the configured XAUUSD symbol. Example response: `{symbol, bid, ask, spread, time}`.
3. **Bars — `xau_bars`.** `GET /api/xau/bars?timeframe=M5&count=100` ($0.020). `timeframe` is one of
   `M1 | M5 | M15 | H1`; `count` is an integer **10–500**. Response: `{symbol, timeframe, count,
   bars[{time, open, high, low, close, tick_volume}]}`.
4. **Market state — `xau_market_state`.** `GET /api/xau/market-state` ($0.030). Computed from MT5
   bars: return, ATR, range position, realized volatility, trend slope and session flags.
5. **Optional session clock — `session_state`.** `GET /api/session-state?dateTime=<ISO-8601>`
   ($0.005). Returns `{timezone: "Europe/Vienna", london, newYork, asia, minuteOfDay}`; `dateTime`
   defaults to now.
6. **Combine.** Join on `symbol`; treat `time` on the quote as the snapshot instant. Each route is a
   separate x402 payment — make one 402 preflight per route and pay each once.

## Rules

- Out-of-range `count` or an unknown `timeframe` is not documented to return a specific error; keep to
  the enums and bounds above so you are not charged for a rejected request.
- The feed is a single retail broker terminal, read-only; the provider describes outputs as "component
  scores, not investment advice" on the strategy route and makes no data-quality or latency commitment
  (no SLA is published).
- No refunds and no idempotency — see `flowhomes-eu-discover-then-pay.md` and
  `conventions/flowhomes-eu-conventions.yml`.
