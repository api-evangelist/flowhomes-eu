# Qorevia Market Intelligence

Pay-per-call market intelligence, data profiling and deterministic utilities for autonomous agents.

- Base URL: https://api.flowhomes.eu
- x402 manifest: https://api.flowhomes.eu/.well-known/x402
- OpenAPI: https://api.flowhomes.eu/openapi.json
- Universal finder: https://api.flowhomes.eu/api/find?q=your+need
- MCP discovery/router: https://api.flowhomes.eu/mcp
- A2A Agent Card: https://api.flowhomes.eu/.well-known/agent-card.json
<!-- QOREVIA_V3_5_SKILL_GATEWAY -->
- Founders Network: https://api.flowhomes.eu/api/club
- Machine invite beacon: https://api.flowhomes.eu/.well-known/qorevia-club.json
- Qorevia Afterhours: https://api.flowhomes.eu/party
<!-- QOREVIA_V3_6_SKILL_GROWTH -->
- Agent Magnet: https://api.flowhomes.eu/.well-known/qorevia-magnet.json
- Standard A2A card: https://api.flowhomes.eu/.well-known/agent-card.json
- Legacy A2A alias: https://api.flowhomes.eu/.well-known/agent.json
- Discovery stats: https://api.flowhomes.eu/api/magnet/stats
<!-- QOREVIA_V3_7_SKILL_MAGNET -->
- Payment network: eip155:8453
- Asset: USDC

## Paid tools

- **GET /api/session-state** â€” $0.005 â€” Deterministic trading-session state for London, New York and Asia in Europe/Vienna time; useful for market and execution agents.
- **POST /api/risk-levels** â€” $0.005 â€” Calculate deterministic stop-loss, take-profit, risk/reward and price distances from entry and percentage settings.
- **POST /api/strategy-grade** â€” $0.020 â€” Deterministic strategy robustness score from trades, profit factor, win rate, drawdown and walk-forward pass rate; returns component scores, not investment advice.
- **GET /api/xau/quote** â€” $0.010 â€” Live XAUUSD bid/ask/last/spread snapshot from a read-only local MetaTrader 5 terminal.
- **GET /api/xau/bars** â€” $0.020 â€” Recent XAUUSD OHLCV bars from a read-only local MetaTrader 5 terminal. Supports M1/M5/M15/H1 and bounded counts.
- **GET /api/xau/market-state** â€” $0.030 â€” Computed XAUUSD market state from MT5 bars: return, ATR, range position, realized volatility, trend slope and session flags.
- **POST /api/csv-profile** â€” $0.0025 â€” Profile supplied CSV locally: rows, columns, missing values, unique counts, inferred types and numeric statistics. No external API or data retention.
- **POST /api/json-shape** â€” $0.0025 â€” Describe the structural shape of supplied JSON locally using normalized paths, observed value types and occurrence counts. No external API or data retention.
- **POST /api/jwt-decode** â€” $0.0025 â€” Decode JWT header and payload without signature verification
- **POST /api/tick-pnl** â€” $0.050 â€” Calculate PnL from entry exit contracts tick size and tick value
- **POST /api/evm-address-syntax** â€” $0.010 â€” Validate basic EVM 20-byte hex address syntax
- **POST /api/ohlcv-state** â€” $0.0025 â€” Compute simple return range position and true-range average from supplied OHLCV bars
- **POST /api/regex-test** â€” $0.0034 â€” Run a supplied JavaScript regular expression against supplied text

Clients should make the request normally, read the HTTP 402 payment requirements, pay using x402, and retry with PAYMENT-SIGNATURE.
