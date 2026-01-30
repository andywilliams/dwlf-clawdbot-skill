# 📊 DWLF Clawdbot Skill

A [Clawdbot](https://github.com/clawdbot/clawdbot) skill that gives your agent native access to [DWLF](https://dwlf.co.uk) — a market analysis platform for crypto and stocks.

Ask your agent things like:
- "How's BTC looking?"
- "What signals fired today?"
- "Show me support/resistance levels for TSLA"
- "Run a backtest on my Golden Cross strategy"
- "Log a long on ETH at 3,200"

## What's DWLF?

DWLF turns market noise into semantic data — support/resistance levels, indicator events, trade signals, backtests, and more. This skill lets your Clawdbot agent tap into all of it conversationally.

## Setup

### 1. Install the skill

Copy this skill into your Clawdbot workspace:

```bash
cd ~/clawd/skills
git clone https://github.com/andywilliams/dwlf-clawdbot-skill.git dwlf
```

### 2. Get an API key

1. Sign up at [dwlf.co.uk](https://dwlf.co.uk)
2. Go to **Settings → API Keys**
3. Click **Generate Key** — name it something like "Clawdbot"
4. Copy the key (`dwlf_sk_...`)

### 3. Configure auth

Add your API key to `TOOLS.md` in your workspace:

```markdown
## DWLF
- API Key: dwlf_sk_your_key_here
```

Or set the environment variable:

```bash
export DWLF_API_KEY="dwlf_sk_your_key_here"
```

### 4. Use it

Just talk to your agent about markets. The skill triggers automatically on topics like market analysis, trading signals, backtests, portfolio, indicators, support/resistance, etc.

## What's Included

```
dwlf/
├── SKILL.md              # Procedural instructions (loaded by Clawdbot)
├── scripts/
│   └── dwlf-api.sh      # Generic API wrapper (curl + jq)
└── references/
    └── api-endpoints.md  # Full endpoint reference (188+ endpoints)
```

## Capabilities

| Feature | Examples |
|---------|---------|
| **Market Data** | Price, OHLCV candles, volume |
| **Technical Indicators** | RSI, EMA, MACD, Bollinger Bands, DSS, Ichimoku, and more |
| **Support/Resistance** | Auto-detected levels with confidence scores |
| **Trendlines** | Auto-detected with slope and touch points |
| **Events** | Breakouts, crossovers, divergences, candlestick patterns |
| **Strategies** | Create, view, and manage visual signal strategies |
| **Backtesting** | Run backtests with win rate, Sharpe ratio, P&L |
| **Trade Signals** | Active signals, recent history, performance stats |
| **Portfolio** | Track holdings, P&L, snapshots |
| **Trade Journal** | Log trades, add notes, track executions |
| **Watchlist** | Monitor symbols |
| **Custom Events** | Define your own indicator-based events |

## Symbol Format

- **Crypto:** `BTC-USD`, `ETH-USD`, `SOL-USD`
- **Stocks/ETFs:** `TSLA`, `NVDA`, `META`, `MARA`
- **Forex:** `GBP-USD`, `EUR-USD`

## Also Available: MCP Server

Want to use DWLF from Claude Desktop, Codex, Cursor, or any MCP client? Check out the companion project:

👉 [dwlf-mcp-server](https://github.com/andywilliams/dwlf-mcp-server)

## License

MIT
