# AO Optimiser - TradingView Pine Script Strategy v0.8.0

## 🎯 Project Overview

AO Optimiser is a sophisticated TradingView Pine Script v6 **strategy** designed for **high-volume watchlist scanning** that analyzes external trading signals through advanced statistical analysis, risk management, and **profit-validated filtering**.

### ⚡ **v0.8.0 - DUAL MODE SYSTEM**
- **Optimised Mode**: Auto-calculates TP/SL levels + validates profitability from historical data
- **Custom Mode**: Manual control over filter thresholds with historical validation
- **Smart Position Sizing**: Fixed 2% default (adjustable in Properties tab)
- **Always-On Features**: Strict validation, continuous data collection, historical tracking

### 🔑 Current Features

- **Dual Filter Modes**: Choose between auto-optimised or manual control
- **Profitability Validation**: Only trades when historical simulation predicts profit
- **External Signal Integration**: Connects to external indicators with standardized signal format
- **Demo Signal Connector**: Auto-generates signals based on price movement thresholds
- **Strategy-Based Execution**: Real trades with built-in backtesting and performance tracking
- **Visual Labels**: Always-visible signal labels with filter and trade status
- **Live Dashboard**: Mode-specific metrics showing validation status and expected performance
- **Multi-TP System**: Partial exits at TP1 (50%), TP2 (remaining)

## 🎮 **Dual Mode System**

### ⚡ **Optimised Mode** (Recommended for experienced users)
**Fully automated - calculates everything from historical data:**
- **TP1**: 90% confidence level (conservative target)
- **TP2**: Average profit of TP1 winners OR 50th percentile fallback
- **SL**: Historical average drawdown
- **Profitability Check**: Simulates historical performance, only trades if profitable
- **Success Rate**: Calculates expected win rate with optimised levels

**Dashboard shows:**
- Expected profit per trade (e.g., "+2.2%/trade")
- Risk/Reward validation (SL < TP2)
- Expected success rate percentage

### 🎯 **Custom Mode** (Recommended for learning/testing)
**Manual control with historical validation:**
- **TP1 Success Rate**: Minimum required hit rate (default: 90%)
- **TP1 Min Level**: Minimum profit threshold (default: 0.5%)
- **Max Drawdown**: Maximum acceptable drawdown (default: 2.1%)
- **Risk/Reward**: Automatic validation (SL < TP2)

**Dashboard shows:**
- TP1 success rate validation (PASS/FAIL)
- TP1 level threshold check
- Drawdown limit compliance

## 🚀 Quick Start

### Installation
1. Download [`src/ao_optimiser.pine`](src/ao_optimiser.pine)
2. Open TradingView → Pine Script Editor  
3. Create new **Strategy** (not indicator)
4. Copy and paste the code
5. Save and add to chart

### Optimised Mode Setup (Auto-Everything)
