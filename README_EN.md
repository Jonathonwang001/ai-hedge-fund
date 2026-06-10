# 🏛️ AI Hedge Fund — The Twelve-Member Investment Committee v3.0

> *"It's far better to buy a wonderful company at a fair price than a fair company at a wonderful price." — Warren Buffett*
>
> *"He who lives by the crystal ball is destined to eat ground glass." — Ray Dalio*
>
> *"Innovation solves problems. We invest in companies solving the world's biggest problems." — Cathie Wood*

[中文](README.md) | [About](ABOUT_EN.md)

---

## 📈 Overview

AI Hedge Fund is an **AI-powered multi-agent investment analysis system**. It simulates 12 legendary investors with complete distilled personalities — mental models, decision heuristics, expression DNA, anti-patterns, and honesty boundaries — through a formal committee debate protocol to generate consensus-driven investment recommendations.

**v3.0 Core Upgrade**: Full 12-member committee with Ray Dalio and Cathie Wood complete personality distillation (based on all public books/videos/interviews).

### 🏛️ The Twelve

| # | Member | Firm | Core Philosophy |
|---|--------|------|-----------------|
| 1 | **Warren Buffett** | Berkshire Hathaway | Value: wonderful companies at fair prices |
| 2 | **Charlie Munger** | Berkshire Hathaway | Mental models + "Invert, always invert" |
| 3 | **Ben Graham** | Graham-Newman | Margin of safety + Mr. Market |
| 4 | **Ray Dalio** 🔥 | Bridgewater Associates | Economic machine + All-Weather + Principles |
| 5 | **Cathie Wood** 🔥 | ARK Invest | Disruptive innovation + Wright's Law + 5Y horizon |
| 6 | **Bill Ackman** | Pershing Square | Activist + concentrated + moat |
| 7 | **Stanley Druckenmiller** | Duquesne Capital | Asymmetric bets + liquidity first |
| 8 | **George Soros** | Quantum Fund | Reflexivity + boom/bust cycles |
| 9 | **Paul Tudor Jones** | Tudor Investment | Macro cycles + risk first |
| 10 | **Jim Simons** | Renaissance Technologies | Quantitative + stat arb + anti-narrative |
| 11 | **Technical Analyst** | — | Price action + indicators |
| 12 | **Risk Manager** | — | Volatility + position sizing + VaR |

**22 distilled agent implementations available** — the remaining 15 (Richard Dennis, Steve Cohen, Carl Icahn, Ken Griffin, etc.) on-demand.

---

## 🔥 Committee Debate Protocol

```
Phase 1: Parallel Independent Analysis
  → Each of 12 members: signal + confidence (0-100) + reasoning

Phase 2: Structured Debate
  → Bullish members make their case
  → Bearish members challenge
  → Ray Dalio cross-examines everyone's macro assumptions
  → Cathie Wood cross-examines everyone's innovation blind spots

Phase 3: Consensus Building
  → STRONG_BULLISH / BULLISH / MIXED / BEARISH / STRONG_BEARISH

Phase 4: Portfolio Manager Final Recommendation
  → Synthesized output + Risk Manager 5-tier position sizing
```

---

## 🚀 Quick Start

```bash
git clone https://github.com/Jonathonwang001/ai-hedge-fund.git
cd ai-hedge-fund
pip install -r requirements.txt

# Full committee analysis
python3 investment_committee.py --ticker AAPL

# Select specific masters
python3 investment_committee.py --ticker TSLA --masters buffett,dalio,wood,soros

# Formal debate mode
python3 investment_committee.py --ticker NVDA --debate
```

### Python API

```python
from investment_committee import InvestmentCommittee

committee = InvestmentCommittee()
report = committee.analyze("AAPL", data=market_data)

print(f"Consensus: {report.consensus}")
print(f"Bullish: {report.bullish_count}/12, Bearish: {report.bearish_count}/12")
for opinion in report.expert_opinions:
    print(f"  {opinion.name}: {opinion.signal} ({opinion.confidence}%)")
```

---

## 📊 Sample Output

```json
{
  "ticker": "NVDA",
  "committee": {
    "total_members": 12,
    "bullish": 8, "bearish": 2, "neutral": 2,
    "consensus": "BULLISH",
    "average_confidence": 72.5
  },
  "members": {
    "warren_buffett": {"signal": "bullish", "confidence": 80,
      "reasoning": "Dominant GPU/AI moat, 50%+ operating margins, pricing power"},
    "ray_dalio": {"signal": "bullish", "confidence": 75,
      "reasoning": "AI productivity = genuine structural shift. Size accordingly"},
    "cathie_wood": {"signal": "bullish", "confidence": 95,
      "reasoning": "NVDA is the picks-and-shovels of AI. 5-year TAM $10T+"}
  },
  "risk_manager": {
    "recommended_position": "10-12%",
    "var_95": "-8.2%",
    "max_drawdown_risk": "-25% to -35%"
  },
  "recommendation": "BULLISH — Initiate/Add 10-12%. Set stop at -20%"
}
```

---

## 🧠 Architecture

```
Request
  ↓
Data Fetching (Yahoo Finance / API)
  ↓
┌───┴───┬────┬────┬────┬────┬────┬────┬────┬────┬────┬────┬────┐
Buffett Munger Graham Dalio Wood Ackman Druck Soros Jones Simons Tech Risk
└───┬───┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┘
    └──────┴────┴────┴────┴────┴────┴────┴────┴────┴────┴────┘
                            ↓
                 Investment Committee (Debate)
                            ↓
                  Portfolio Manager (Final)
                            ↓
                 Recommendation + Position Size
```

**Nüwa Distillation Framework V2**: Each agent implementation includes:
- Mental Models + evidence sources
- Decision Heuristics + conditions/actions/examples
- Expression DNA + sentence patterns/vocabulary/rhythm
- Anti-Patterns + what they'll never do
- Honesty Boundaries + admitted blind spots

---

## 📦 Feature Modules

| Module | Function | File |
|--------|----------|------|
| Investment Committee | 12-agent parallel analysis + debate + consensus | `investment_committee.py` |
| Core Analysis | Fundamentals + technicals + risk | `ai_hedge_fund.py` |
| Enhanced Agents | Earnings / Wall St / Macro / Dividend | `enhanced_agents.py` |
| Portfolio | MPT optimization + committee weighting | `portfolio_constructor.py` |
| Backtesting | Strategy backtest + multi-strategy comparison | `backtester.py` |
| Rebalancing | Drift monitoring + signal triggers | `rebalance_monitor.py` |
| Tax Optimization | Tax-loss harvesting + wash sale detection | `tax_optimizer.py` |
| ESG Screening | Environmental / Social / Governance scoring | `esg_screener.py` |
| Hot & Rumor Scanner | Trending stocks / M&A / insider activity | `hot_rumor_scanner.py` |
| Circle of Competence | Industry knowledge assessment | `circle_of_competence.py` |

---

## ⚠️ Disclaimer

**⚠️ IMPORTANT**: This project is for **educational and research purposes only**.

- **Not investment advice**: This is AI simulation, not professional financial advice
- **No guarantee**: Past performance does not predict future results
- **Data limitations**: Free data sources may have delays or inaccuracies
- **Risk**: Always consult a qualified financial advisor before investing

---

## 📚 Related Projects

- [new-investment-brain](https://github.com/Jonathonwang001/new-investment-brain) — Six-brain deep analysis + 11-member investment committee
- [industry-deep-driller](https://github.com/Jonathonwang001/industry-deep-driller) — Industry chain deep drilling + chokepoint identification

---

**Version**: 3.0.0 — Twelve-Member Committee  
**License**: MIT  
**Author**: OpenClaw Community  
**Last Updated**: 2026-06-10
