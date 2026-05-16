# AI Hedge Fund

An AI-powered hedge fund team that simulates legendary investors (Buffett, Munger, Graham, etc.) to analyze stocks and provide investment recommendations using multi-agent consensus.

## Overview

This project creates a team of AI agents, each embodying the investment philosophy of famous investors:

### Classic Investment Agents (5)
- **Warren Buffett** - Value investing, wonderful companies at fair prices
- **Ben Graham** - Margin of safety, hidden gems
- **Charlie Munger** - Mental models, inverted thinking
- **Technical Analyst** - Chart patterns and indicators
- **Risk Manager** - Risk metrics and position sizing

### Enhanced Analysis Agents (4)
- **Earnings Analyst** - EPS surprises, beat rates, earnings quality
- **Wall Street Consensus** - Analyst ratings, price targets, upside
- **Macro Strategist** - VIX, market regime, SPY/QQQ trends
- **Dividend Investor** - Yield, payout safety, dividend growth

**Total: 9 agents analyzing each stock for comprehensive coverage**

## Installation

```bash
# Clone the repository
git clone https://github.com/Jonathonwang001/ai-hedge-fund.git
cd ai-hedge-fund

# Install dependencies
pip install -r requirements.txt
```

## Requirements

```
yfinance
pandas
numpy
beautifulsoup4
requests
alpha_vantage
```

## Usage

### Analyze a Stock

```bash
python ai_hedge_fund.py AAPL
python ai_hedge_fund.py AAPL --detailed
```

### Portfolio Analysis

```bash
python portfolio_constructor.py AAPL,MSFT,GOOGL
```

### Backtest

```bash
python backtester.py AAPL,MSFT --start 2023-01-01 --end 2024-01-01
```

### Market Intelligence

```bash
python news_analyst.py AAPL
python hot_rumor_scanner.py
```

## Architecture

The system uses a multi-agent architecture where each agent represents a famous investor or analyst. Agents analyze stocks from their unique perspective and provide recommendations. A final consensus is reached by weighing all agent opinions.

## License

MIT License

## Disclaimer

This is for educational purposes only. Not financial advice.
