# The E-Money Game: Parameter Specification for Agent Testing (V2)

## Overview

This document is a direct extension of `GAME_FRAMEWORK.md`. Where the original framework establishes the **strategic philosophy** of the E-Money Game, this V2 specification translates that philosophy into **quantitative parameters** required to simulate, test, and benchmark agent strategies and profitability. Without these parameters, the framework cannot be executed computationally.

The concept is approximately **65% complete** from a strategic standpoint. This document addresses the remaining **35%** — the numerical and mechanical layer that makes the game playable and testable.

---

## What the Original Framework Defines ✓

The following elements are well-established in `GAME_FRAMEWORK.md` and do **not** need to be redefined:

| Element | Description |
|---|---|
| Portfolio Allocation | 40% Core / 30% Growth / 20% High-Risk / 10% Experimental |
| Position Sizing | Kelly Criterion-based: 0.5–5% of capital per venture |
| Risk Pillars | Avoidance, Reduction, Transfer, Acceptance |
| Growth Avenues | Autonomous AI, Content Creation, Trading, Micro-Opportunities |
| Reinvestment Model | 60% reinvest / 20% reserve / 20% personal income |
| Micro-Opportunity Engine | Hypothesize → Test → Measure → Scale or Kill |
| Advanced Principles | Velocity with Validation, Micro-Niche, Bayesian Growth Engine |

---

## Part I: Initial Game State Parameters

These parameters define the starting conditions for any simulation run.

| Parameter | Description | Recommended Default |
|---|---|---|
| **Starting Capital** | Capital each agent begins with | $100,000 |
| **Number of Agents** | Competing agents per simulation | 4–10 |
| **Game Duration** | Total number of turns | 52 turns (1 simulated year) |
| **Turn Length** | Real-world time each turn represents | 1 week |
| **Victory Condition** | Primary win metric | Highest net capital at game end |
| **Secondary Victory** | Tiebreaker metric | Longest consecutive turns above starting capital |
| **Elimination Threshold** | Capital floor triggering agent removal | $1,000 (1% of start) |

---

## Part II: Venture-Specific Parameters

For each of the four growth avenues, the following numerical parameters are required to simulate outcomes.

### Avenue I: Autonomous AI Businesses

> Portfolio classification: Growth → Core (matures over time)

| Parameter | Value | Notes |
|---|---|---|
| **Base Success Rate** | 25% | Probability of generating positive return |
| **Return Multiplier (Success)** | 3.0× | Capital returned on a successful venture |
| **Capital Loss (Failure)** | −80% | Percentage of investment lost on failure |
| **Time to Result** | 3 turns | Turns before outcome is revealed |
| **Operational Cost** | 2% per turn | Ongoing cost while venture is active |
| **Maximum Capital per Venture** | $50,000 | Hard cap on single investment |
| **Maturity Bonus** | +10% return per 10 turns survived | Reward for long-term stability |

### Avenue II: AI Model and Content Creation

> Portfolio classification: Experimental → Growth → Core (full spectrum)

| Parameter | Value | Notes |
|---|---|---|
| **Base Success Rate** | 40% | Higher success rate, lower ceiling |
| **Return Multiplier (Success)** | 2.0× | Moderate return on success |
| **Capital Loss (Failure)** | −50% | Partial recovery possible |
| **Time to Result** | 2 turns | Faster feedback loop |
| **Operational Cost** | 1% per turn | Lower maintenance cost |
| **Maximum Capital per Venture** | $30,000 | |
| **Viral Event Probability** | 5% per turn | Random chance of 10× multiplier |

### Avenue III: Trading and Algorithmic Systems

> Portfolio classification: High-Risk / High-Reward

| Parameter | Value | Notes |
|---|---|---|
| **Base Success Rate** | 15% | Low probability, high reward |
| **Return Multiplier (Success)** | 10.0× | Asymmetric upside |
| **Capital Loss (Failure)** | −95% | Near-total loss on failure |
| **Time to Result** | 1 turn | Fastest feedback of all avenues |
| **Operational Cost** | 5% per turn | High infrastructure cost |
| **Maximum Capital per Venture** | $20,000 | Enforces position sizing discipline |
| **Drawdown Recovery Time** | 3 turns | Turns before agent can reinvest in this avenue after a loss |

### Avenue IV: Micro-Opportunities

> Portfolio classification: Experimental (10% fund)

| Sub-Type | Discovery Rate | Success Rate | Return (Success) | Loss (Failure) | Time to Result |
|---|---|---|---|---|---|
| **Niche Arbitrage** | 15% per turn | 35% | 4.0× | −90% | 1 turn |
| **Skill Arbitrage** | 10% per turn | 45% | 2.5× | −60% | 3 turns |
| **Content Arbitrage** | 20% per turn | 30% | 3.0× | −70% | 2 turns |
| **Micro-SaaS** | 5% per turn | 20% | 8.0× | −85% | 5 turns |

> **Discovery Rate**: Probability per turn that an opportunity of this type becomes available to the agent.

---

## Part III: Market Dynamics Parameters

These parameters govern the external environment that all agents operate within.

| Parameter | Value | Description |
|---|---|---|
| **Base Market Volatility** | ±15% per cycle | Standard deviation of market-wide return modifier |
| **Bull Market Duration** | 8–16 turns (random) | Turns where success rates are boosted by +10% |
| **Bear Market Duration** | 4–8 turns (random) | Turns where success rates are reduced by −15% |
| **Black Swan Probability** | 2% per turn | Chance of a market-wide shock event |
| **Black Swan Impact** | −40% to all active ventures | Applied to all agents simultaneously |
| **Opportunity Scarcity** | Reduces discovery rate by 5% per additional agent in same avenue | Simulates competition |
| **First-Mover Advantage** | +15% return for first agent to enter a new opportunity | Rewards speed |

---

## Part IV: Portfolio Mechanics

### Rebalancing Rules

| Parameter | Value |
|---|---|
| **Rebalancing Frequency** | Once per 4 turns (monthly equivalent) |
| **Rebalancing Cost** | 0.5% of capital moved |
| **Tolerance Band** | ±5% from target allocation before forced rebalancing |

### Reserve Fund Mechanics

The 20% reserve ("longevity fund") operates under the following rules:

| Rule | Specification |
|---|---|
| **Reserve Growth Rate** | 3% per 12 turns (annualized low-risk return) |
| **Withdrawal Condition** | Only accessible when active capital falls below 30% of starting capital |
| **Withdrawal Limit** | Maximum 50% of reserve per event |
| **Replenishment Rule** | 20% of all future profits until reserve is restored |

---

## Part V: Agent Decision Parameters

These parameters define the decision-making mechanics available to each agent per turn.

| Parameter | Value | Description |
|---|---|---|
| **Actions per Turn** | 3 | Maximum number of investment decisions per turn |
| **Information Lag** | 0 turns (default) | Turns before agent learns outcome; can be set to 1–3 for harder modes |
| **Learning Rate (Bayesian)** | 0.2 | Weight given to new evidence when updating success probability estimates |
| **Exploration Budget** | Capped at 10% of capital | Enforces the Experimental fund limit |
| **Portfolio Review Frequency** | Every turn | Agents assess portfolio state each turn |

### Agent Archetype Configurations

Pre-built agent strategy profiles for testing:

| Archetype | Core | Growth | High-Risk | Experimental | Risk Tolerance |
|---|---|---|---|---|---|
| **Conservative** | 60% | 25% | 10% | 5% | Low |
| **Balanced (Framework)** | 40% | 30% | 20% | 10% | Medium |
| **Aggressive** | 20% | 20% | 45% | 15% | High |
| **Explorer** | 25% | 25% | 25% | 25% | Very High |
| **Trader** | 20% | 10% | 60% | 10% | Extreme |

---

## Part VI: Scoring and Victory Conditions

### Primary Score: Net Capital

```
Final Score = Active Capital + Reserve Fund + Unrealized Venture Value
```

### Secondary Metrics (for agent benchmarking)

| Metric | Description | Weight |
|---|---|---|
| **Survival Rate** | Percentage of turns agent remained solvent | 20% |
| **Sharpe Ratio** | Return per unit of risk taken | 20% |
| **Max Drawdown** | Largest peak-to-trough capital decline | 15% |
| **Portfolio Diversity Score** | Adherence to allocation targets | 10% |
| **Reinvestment Discipline** | Compliance with 60/20/20 split | 10% |
| **Capital Growth Rate** | Compound growth rate over game duration | 25% |

### Composite Agent Score

```
Composite Score = (0.25 × Capital Growth Rate)
               + (0.20 × Survival Rate)
               + (0.20 × Sharpe Ratio)
               + (0.15 × (1 − Max Drawdown))
               + (0.10 × Portfolio Diversity Score)
               + (0.10 × Reinvestment Discipline)
```

---

## Part VII: Simulation Modes

| Mode | Success Rate Modifier | Volatility | Black Swan Freq | Recommended For |
|---|---|---|---|---|
| **Sandbox** | +20% | ±5% | 0% | Initial agent calibration |
| **Normal** | Baseline | ±15% | 2%/turn | Standard benchmarking |
| **Hard** | −10% | ±25% | 5%/turn | Stress testing longevity |
| **Extreme** | −25% | ±40% | 10%/turn | Adversarial agent testing |

---

## Part VIII: Validation Criteria

A correctly implemented simulation should satisfy the following observable properties:

1. **Balanced agents outperform extremes** over 52-turn runs on average, validating the 40/30/20/10 framework.
2. **Conservative agents survive longer** but accumulate less capital than Aggressive agents.
3. **Aggressive agents win more often in Bull markets** but are eliminated more frequently in Bear markets.
4. **Reserve fund usage** should correlate with Bear market events.
5. **No single strategy should win 100% of simulations**, confirming the role of variance.
6. **Bayesian learning agents** should outperform static agents over longer game durations (100+ turns).

---

## Summary of New Parameters Introduced in V2

| Category | Parameters Added |
|---|---|
| Initial Game State | 7 |
| Venture-Specific (per avenue) | 28 |
| Market Dynamics | 7 |
| Portfolio Mechanics | 8 |
| Agent Decision Rules | 5 |
| Scoring & Victory | 7 |
| Simulation Modes | 4 |
| **Total New Parameters** | **66** |

---

*This document should be read in conjunction with `GAME_FRAMEWORK.md`. The strategic philosophy defined there remains the authoritative source; this V2 specification exists solely to operationalize it for computational simulation and agent benchmarking.*
