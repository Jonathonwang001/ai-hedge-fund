---
title: AI Hedge Fund 工具地图
source: ai-hedge-fund skill installation
created: 2026-04-13
updated: 2026-04-13
tags: [tool-map, ai-hedge-fund, skill, integration]
source_file: ~/.qclaw/workspace/skills/ai-hedge-fund/
---

# AI Hedge Fund 技能工具地图

> **来源**: `https://github.com/erongcao/ai-hedge-fund-skill`
> **安装时间**: 2026-04-13
> **版本**: V2 女娲版

---

## 📁 技能目录结构

```
~/.qclaw/workspace/skills/ai-hedge-fund/
├── ai_hedge_fund.py          # ⭐ V1 主程序（1754行）
├── ai_hedge_fund_advanced.py # V2 增强版
├── hedge_cli.py              # ⭐ 统一命令行入口
├── investment_committee.py   # ⭐ 投资委员会（多大师共识）
├── portfolio_constructor.py  # ⭐ 组合构建（Markowitz优化）
├── backtest_engine.py        # ⭐ 回测引擎
├── backtester.py             # ⭐ 回测CLI
├── realtime_data_feed.py     # 实时数据（WebSocket）
├── smart_data_fetcher.py     # 智能数据获取
├── hot_rumor_scanner.py      # 🔥 热股+谣言扫描
├── news_analyst.py           # 新闻分析
├── esg_screener.py           # ESG筛选
├── circle_of_competence.py   # 能力圈检测
├── rebalance_monitor.py      # 再平衡监控
├── tax_optimizer.py          # 税务优化
├── visualizer.py             # 可视化
├── data_enhancement.py        # 数据增强
├── data_freshness.py         # 数据新鲜度检测
├── adaptive_weights.py       # 自适应权重
├── graceful_degrade.py       # 优雅降级
├── two_tier_architecture.py  # 双层架构
├── industry_rules.py         # 行业规则引擎
├── base.py                   # 基础类
├── zero_api_config.py        # 零API配置
├── auto_updater.py           # 自动更新
├── skill.json                # Skill元数据
│
├── [CLI脚本]
│   ├── ai-hedge-fund          # V1单股分析脚本
│   ├── ai-hedge-fund-cli      # ⭐ 统一CLI
│   ├── portfolio-build         # ⭐ 组合构建CLI
│   └── scanner                # ⭐ 扫描器CLI
│
├── [投资大师蒸馏框架 22位]
│   ├── buffett_distilled_v2.py      # 巴菲特 ⭐⭐⭐⭐⭐ (56KB)
│   ├── dalio_distilled_v2.py        # 达利欧 ⭐⭐⭐⭐⭐
│   ├── ben_graham_distilled_v2.py   # 格雷厄姆 ⭐⭐⭐⭐⭐
│   ├── simons_distilled_v2.py       # 西蒙斯（量化）⭐⭐⭐⭐⭐
│   ├── soros_distilled_v2.py        # 索罗斯（反身理论）⭐⭐⭐⭐⭐
│   ├── dennis_distilled_v2.py       # 丹尼斯（海龟交易）⭐⭐⭐⭐
│   ├── cathie_wood_distilled_v2.py  # 伍德（创新/颠覆）⭐⭐⭐⭐
│   ├── jones_pt_distilled_v2.py     # 琼斯（宏观对冲）⭐⭐⭐⭐
│   ├── seykota_distilled_v2.py      # 塞科塔（趋势跟踪）⭐⭐⭐⭐
│   ├── kovner_distilled_v2.py       # 科弗纳（宏观）⭐⭐⭐
│   ├── cohen_distilled_v2.py        # 科恩（特殊情况）⭐⭐⭐
│   ├── druckenmiller_distilled_v2.py # 德鲁肯米勒（宏观）⭐⭐⭐
│   ├── griffin_distilled_v2.py      # 格里芬（固收套利）⭐⭐⭐
│   ├── icahn_distilled_v2.py        # 伊坎（维权投资）⭐⭐⭐
│   ├── einhorn_distilled_v2.py      # 艾因霍恩（做空）⭐⭐⭐
│   ├── loeb_distilled_v2.py         # 勒布（事件驱动）⭐⭐⭐
│   ├── pabrai_distilled_v2.py       # 帕布拉伊（价值/套利）⭐⭐⭐
│   ├── yass_distilled_v2.py         # 雅斯（量化/技术）⭐⭐⭐
│   ├── williams_l_distilled_v2.py   # 威廉姆斯（趋势）⭐⭐⭐
│   ├── livermore_distilled_v2.py    # 利弗莫尔（投机传奇）⭐⭐⭐
│   ├── rogers_jim_distilled_v2.py   # 吉姆·罗杰斯 ⭐⭐⭐
│   └── ackman_distilled_v2.py       # 阿克曼（激进维权）⭐⭐⭐
│
├── [文档]
│   ├── SKILL.md              # 技能说明
│   ├── QUICKSTART.md         # 快速上手
│   ├── README.md             # V2完整说明
│   ├── ADVANCED.md           # 高级功能说明
│   └── *.md（其他文档）
│
└── requirements.txt
```

---

## 🛠️ 核心工具详解

### T001：ai_hedge_fund.py（V1主程序）

**路径**: `~/.qclaw/workspace/skills/ai-hedge-fund/ai_hedge_fund.py`
**CLI包装**: `~/.qclaw/workspace/skills/ai-hedge-fund/ai-hedge-fund`
**行数**: 1754行

**功能**：基础股票分析，5个agent（Buffett/Graham/技术分析师/风险管理/Cathie Wood）

**使用方式**：
```bash
cd ~/.qclaw/workspace/skills/ai-hedge-fund
./ai-hedge-fund AAPL                    # 基础分析
./ai-hedge-fund AAPL --detailed         # 详细分析
./ai-hedge-fund AAPL,MSFT,GOOGL --compare  # 多股对比
./ai-hedge-fund NVDA --json > nvda.json # JSON输出
```

**输出字段**：
- 信号：看涨/看空/中性（带置信度%）
- 各agent判断（5个）
- 关键风险
- 仓位建议（%）

**数据源**：Yahoo Finance（yfinance，免费）

**适用场景**：快速基础分析、周日复盘筛选候选股

---

### T002：hedge_cli.py（统一CLI）

**路径**: `~/.qclaw/workspace/skills/ai-hedge-fund/hedge_cli.py`
**CLI包装**: `~/.qclaw/workspace/skills/ai-hedge-fund/ai-hedge-fund-cli`
**依赖**: investment_committee.py + circle_of_competence.py + realtime_data_feed.py

**功能**：统一命令行，支持多大师共识分析

**使用方式**：
```bash
./ai-hedge-fund-cli fund NVDA                         # 快速分析
./ai-hedge-fund-cli fund NVDA --masters buffett,dalio  # 指定大师
./ai-hedge-fund-cli fund BTC-USDT --timeframe 4H      # 加密货币
./ai-hedge-fund-cli backtest buffett --start 2020-01 --end 2024-12
./ai-hedge-fund-cli compare --masters all --period 1Y
```

**数据源**：yfinance + 实时数据

**适用场景**：深度分析、周日复盘多大师验证

---

### T003：investment_committee.py（投资委员会）

**路径**: `~/.qclaw/workspace/skills/ai-hedge-fund/investment_committee.py`
**调用方式**：Python直接import

```python
from investment_committee import InvestmentCommittee, ConsensusType
committee = InvestmentCommittee()
report = committee.analyze("NVDA", masters=["buffett", "dalio", "graham"])
```

**功能**：
- 22位大师框架参与分析
- 共识类型：STRONG_BULLISH / BULLISH / MIXED / BEARISH / STRONG_BEARISH / UNCLEAR
- 输出置信度、加权评分、详细理由

**适用场景**：周日复盘核心工具、周三市场异动分析

---

### T004：portfolio_constructor.py（组合构建器）

**路径**: `~/.qclaw/workspace/skills/ai-hedge-fund/portfolio_constructor.py`
**CLI包装**: `~/.qclaw/workspace/skills/ai-hedge-fund/portfolio-build`
**行数**: ~500行

**功能**：基于现代投资组合理论（Markowitz）的组合优化

**使用方式**：
```bash
./portfolio-build AAPL,MSFT,GOOGL,NVDA --risk moderate
./portfolio-build NVDA,TSLA --risk aggressive --max-position 0.25
```

**参数**：
- `--risk conservative|moderate|aggressive`
- `--max-position`：单只最大权重（默认20%）
- `--min-position`：单只最小权重（默认2%）

**输出字段**：
- 各标的权重
- 预期收益率
- 波动率
- 夏普比率
- 最大回撤估算
- 分散化评分
- 再平衡建议

**适用场景**：周日复盘Phase 4（构建进攻+防守组合）、调仓建议

---

### T005：backtester.py（回测器）

**路径**: `~/.qclaw/workspace/skills/ai-hedge-fund/backtester.py`
**依赖**: backtest_engine.py

**使用方式**：
```bash
./backtester AAPL,MSFT --start 2023-01-01 --end 2024-01-01
./backtester buffett --start 2020-01 --end 2025-12
```

**输出**：
- 总收益率
- 年化收益率
- 最大回撤
- 夏普比率
- 胜率

**适用场景**：周日复盘Phase 4（回测验证）、策略有效性评估

---

### T006：scanner（热股+谣言扫描器）

**路径**: `~/.qclaw/workspace/skills/ai-hedge-fund/scanner`
**核心文件**: hot_rumor_scanner.py

**使用方式**：
```bash
./scanner hot          # 趋势股+加密货币
./scanner rumor        # 全市场谣言扫描
./scanner rumor -t NVDA # 指定标的谣言
./scanner scan         # 热股+谣言组合
```

**功能**：
- hot：扫描趋势股票和加密货币
- rumor：检测市场谣言和早期信号
- scan：综合扫描

**适用场景**：周三市场异动监测、周日复盘Phase 1（发现机会）

---

### T007：news_analyst.py（新闻分析）

**路径**: `~/.qclaw/workspace/skills/ai-hedge-fund/news_analyst.py`

**功能**：分析新闻对股价的潜在影响

**适用场景**：早盘播报、盘中监测

---

### T008：esg_screener.py（ESG筛选）

**路径**: `~/.qclaw/workspace/skills/ai-hedge-fund/esg_screener.py`

**功能**：基于ESG（环境/社会/治理）筛选股票

**适用场景**：周日复盘Phase 4（筛选负责任投资标的）

---

### T009：circle_of_competence.py（能力圈检测）

**路径**: `~/.qclaw/workspace/skills/ai-hedge-fund/circle_of_competence.py`

**功能**：
- 判断标的是否在AI能力圈内
- 推荐适合分析该标的大师

```python
from circle_of_competence import get_circle_of_competence, get_experts_for_sector
sector = get_circle_of_competence("NVDA")  # 半导体/AI
experts = get_experts_for_sector("tech")    # 推荐科技类大师
```

**适用场景**：所有分析任务的前置判断

---

### T010：rebalance_monitor.py（再平衡监控）

**路径**: `~/.qclaw/workspace/skills/ai-hedge-fund/rebalance_monitor.py`

**功能**：监控组合偏离度，提示再平衡时机

**适用场景**：持仓监控、周日复盘Phase 5

---

### T011：realtime_data_feed.py（实时数据）

**路径**: `~/.qclaw/workspace/skills/ai-hedge-fund/realtime_data_feed.py`

**功能**：WebSocket实时价格接入

**适用场景**：盘中监测、定时任务实时价格获取

---

### T012：smart_data_fetcher.py（智能数据获取）

**路径**: `~/.qclaw/workspace/skills/ai-hedge-fund/smart_data_fetcher.py`

**功能**：多数据源智能切换，优雅降级

**适用场景**：所有数据获取任务的底层支撑

---

## 🎯 工具选择决策矩阵

| 场景 | 推荐工具 | 说明 |
|------|---------|------|
| 快速基础分析 | T001 ai_hedge_fund.py | 5 agent，免费数据，最快 |
| 多大师深度共识 | T003 investment_committee.py | 22位大师，可选参与 |
| 周日复盘构建最优组合 | T004 portfolio_constructor.py | Markowitz优化 |
| 策略回测验证 | T005 backtester.py | 历史验证 |
| 市场异动监测 | T006 scanner | 热股+谣言 |
| 盘中新闻监测 | T007 news_analyst.py | 新闻影响 |
| 能力圈判断 | T009 circle_of_competence.py | 前置判断 |
| 再平衡建议 | T010 rebalance_monitor.py | 持仓监控 |
| 实时价格 | T011 realtime_data_feed.py | WebSocket |

---

## 🔗 与现有工具的协同关系

```
ai-hedge-fund 工具
├── T001-T003（分析层）→ 输出：信号、置信度、共识
│   ↓ 协同 ↓
├── T004（组合层）→ 输入：候选标的 → 输出：最优权重
│   ↓ 协同 ↓
├── T005（回测层）→ 验证T004的组合效果
│   ↓ 协同 ↓
└── T006（扫描层）→ 发现新标的 → 输入T001-T003循环

与现有系统的关系：
├── technical_indicators.py（已有）→ 补充技术面数据 → 输入T001
├── monte_carlo.py（已有）→ 风险模拟 → T004的验证层
├── financial_scorer.py（已有）→ 基本面打分 → T001的前置筛选
└── AKShare/Finnhub → 数据源 → T012 smart_data_fetcher
```

---

## ⚠️ 使用限制

1. **数据源**：默认使用 Yahoo Finance（yfinance），免费但可能有限制
2. **API Key**（可选）：
   - `FINANCIAL_DATASETS_API_KEY` — 增强财务指标
   - `ALPHA_VANTAGE_API_KEY` — 备选数据源
3. **免责声明**：本工具仅供教育/研究目的，不构成投资建议
4. **代理规则**：Finnhub/Alpha Vantage 需要代理（小火箭: http://127.0.0.1:1082）
5. **Python依赖**：yfinance, pandas, numpy, requests（已安装）

---

## 📝 使用示例（周日复盘场景）

```bash
# 1. 扫描市场机会
./scanner hot

# 2. 用投资委员会深度分析候选股
./ai-hedge-fund-cli fund NVDA --masters buffett,dalio,wood

# 3. 构建最优组合
./portfolio-build NVDA,TSLA,AAPL,MSFT --risk moderate

# 4. 回测验证
./backtester buffett --start 2023-01-01 --end 2026-01-01
```
