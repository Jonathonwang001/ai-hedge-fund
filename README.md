# 🏛️ AI Hedge Fund — 十二位投资大师委员会 v3.0

> *"It's far better to buy a wonderful company at a fair price than a fair company at a wonderful price." — Warren Buffett*
>
> *"He who lives by the crystal ball is destined to eat ground glass." — Ray Dalio*
>
> *"Innovation solves problems. We invest in companies solving the world's biggest problems." — Cathie Wood*

[English](README_EN.md) | [关于本项目](ABOUT.md)

---

## 📈 项目概述

AI Hedge Fund 是一个**AI驱动的多智能体投资分析系统**。它模拟12位传奇投资者的完整投资心智模型，通过正式的委员会辩论流程，对任何股票进行多维度分析并生成共识建议。

**v3.0 核心升级**: 12位委员投资委员会，Ray Dalio 和 Cathie Wood 完整人格蒸馏（基于全部公开书籍/视频/访谈）。

### 🏛️ 12位委员

| # | 委员 | 机构 | 核心哲学 |
|---|------|------|---------|
| 1 | **Warren Buffett** | Berkshire Hathaway | 价值投资：以合理价格买入优秀企业 |
| 2 | **Charlie Munger** | Berkshire Hathaway | 心智模型格栅 + "反过来想" |
| 3 | **Ben Graham** | Graham-Newman | 安全边际 + 市场先生 |
| 4 | **Ray Dalio** 🔥 | Bridgewater Associates | 经济机器 + 全天候策略 + 《原则》 |
| 5 | **Cathie Wood** 🔥 | ARK Invest | 颠覆式创新 + Wright's Law + 5年视角 |
| 6 | **Bill Ackman** | Pershing Square | 激进投资 + 集中持仓 |
| 7 | **Stanley Druckenmiller** | Duquesne Capital | 非对称押注 + 流动性第一 |
| 8 | **George Soros** | Quantum Fund | 反身性理论 + 繁荣/萧条序列 |
| 9 | **Paul Tudor Jones** | Tudor Investment | 宏观周期 + Risk First |
| 10 | **Jim Simons** | Renaissance Technologies | 量化 + 统计套利 + 反叙事 |
| 11 | **Technical Analyst** | — | 量价指标 + 趋势判断 |
| 12 | **Risk Manager** | — | 波动率 + 仓位分级 + VaR |

**22位蒸馏大师代码实现已就绪**，其余15位按需调用（Richard Dennis, Steve Cohen, Carl Icahn, Ken Griffin 等）。

---

## 🔥 正式委员会辩论协议

```
Phase 1: 12人并行独立分析
  → 每人输出: 信号(bullish/bearish/neutral) + 置信度(0-100) + 推理

Phase 2: 辩论环节
  → 看多方阐述
  → 看空方挑战
  → Ray Dalio 挑战所有人的宏观假设
  → Cathie Wood 挑战所有人的创新盲区

Phase 3: 共识构建
  → STRONG_BULLISH / BULLISH / MIXED / BEARISH / STRONG_BEARISH

Phase 4: 仓位分配
  → Portfolio Manager 终审 + Risk Manager 五档建议
```

---

## 🚀 快速开始

```bash
# 克隆仓库
git clone https://github.com/Jonathonwang001/ai-hedge-fund.git
cd ai-hedge-fund
pip install -r requirements.txt

# 完整委员会分析
python3 investment_committee.py --ticker AAPL

# 选择特定委员
python3 investment_committee.py --ticker TSLA --masters buffett,dalio,wood,soros

# 正式辩论模式
python3 investment_committee.py --ticker NVDA --debate
```

### Python API

```python
from investment_committee import InvestmentCommittee

committee = InvestmentCommittee()
report = committee.analyze("AAPL", data=market_data)

print(f"共识: {report.consensus}")
print(f"看多: {report.bullish_count}/12, 看空: {report.bearish_count}/12")
for opinion in report.expert_opinions:
    print(f"  {opinion.name}: {opinion.signal} ({opinion.confidence}%)")
```

---

## 📊 委员会输出示例

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
      "reasoning": "AI GPU护城河极深，50%+营业利润率，定价权"},
    "ray_dalio": {"signal": "bullish", "confidence": 75,
      "reasoning": "AI生产力浪潮=真实结构性转变。但估值反映乐观——控制仓位"},
    "cathie_wood": {"signal": "bullish", "confidence": 95,
      "reasoning": "NVDA是AI革命的'镐和铲'。5年TAM超$10万亿。Wright's Law适用"}
  },
  "risk_manager": {
    "recommended_position": "10-12%",
    "var_95": "-8.2%",
    "max_drawdown_risk": "-25%至-35%"
  },
  "recommendation": "看多——建仓/加仓10-12%。止损设在-20%"
}
```

---

## 🧠 技术架构

```
请求
  ↓
数据获取 (Yahoo Finance/serper/API)
  ↓
┌───┴───┬────┬────┬────┬────┬────┬────┬────┬────┬────┬────┬────┐
Buffett Munger Graham Dalio Wood Ackman Druck Soros Jones Simons Tech Risk
└───┬───┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┴──┬─┘
    └──────┴────┴────┴────┴────┴────┴────┴────┴────┴────┴────┘
                            ↓
                    投资委员会(辩论)
                            ↓
                     仓位管理器(终审)
                            ↓
                   推荐 + 仓位建议
```

**女娲蒸馏框架 V2**: 每位委员的代码实现包含:
- 心智模型(Mental Models) + 证据来源
- 决策启发式(Decision Heuristics) + 条件/行动/案例
- 表达DNA(Expression DNA) + 句式/词汇/节奏
- 反模式(Anti-Patterns) + 永远不做的事
- 诚实边界(Honesty Boundaries) + 承认的盲区

---

## 📦 功能模块

| 模块 | 功能 | 文件 |
|------|------|------|
| 投资委员会 | 12人并行分析+辩论+共识 | `investment_committee.py` |
| 核心分析 | 基本面+技术+风险管理 | `ai_hedge_fund.py` |
| 增强代理 | 财报/华尔街共识/宏观/分红 | `enhanced_agents.py` |
| 投资组合 | MPT优化+委员会权重 | `portfolio_constructor.py` |
| 回测引擎 | 策略回测+多策略对比 | `backtester.py` |
| 再平衡 | 漂移监控+信号触发 | `rebalance_monitor.py` |
| 税务优化 | 亏损收割+洗售检测 | `tax_optimizer.py` |
| ESG筛选 | 环境/社会/治理评分 | `esg_screener.py` |
| 热点扫描 | 热门股+M&A+内幕 | `hot_rumor_scanner.py` |
| 能力圈 | 行业知识评估 | `circle_of_competence.py` |

---

## ⚠️ 免责声明

**⚠️ 重要**: 本项目仅供**教育和研究用途**。

- **不构成投资建议**: 此为AI模拟，非专业金融建议
- **不保证收益**: 过往表现不代表未来结果
- **数据可能延迟**: 免费数据源可能有时间差或不准确
- **风险自负**: 在投资前请咨询持牌财务顾问

---

## 📚 相关项目

- [new-investment-brain](https://github.com/Jonathonwang001/new-investment-brain) — 六大脑深度分析+11人投资委员会
- [industry-deep-driller](https://github.com/Jonathonwang001/industry-deep-driller) — 产业链深度钻探+瓶颈识别

---

**Version**: 3.0.0 — Twelve-Member Committee  
**License**: MIT  
**Author**: OpenClaw Community  
**Last Updated**: 2026-06-10
