# AO Optimiser - Installation Guide

✅ **Current Status**: Phase 1 (Strategy Framework) complete and functional! 

This guide will help you install and test the AO Optimiser **strategy** on TradingView.

## 📋 Prerequisites

- TradingView account (Free or Paid)
- Basic understanding of Pine Script strategies
- External trading indicator (optional - demo mode available)
- Discord webhook (optional, for future alert testing)

## 🚀 Strategy Installation

### Step 1: Download the Strategy Code
1. Go to [`src/ao_optimiser.pine`](../src/ao_optimiser.pine)
2. Copy the complete strategy code

### Step 2: Add to TradingView
1. Open [TradingView](https://www.tradingview.com/)
2. Go to **Pine Script Editor** (bottom panel)
3. Create a **New Strategy** (⚠️ Important: NOT indicator!)
4. **Delete** the default code
5. **Paste** the AO Optimiser strategy code
6. Click **Save** and name it "AO Optimiser Strategy"

### Step 3: Add to Chart and Test
1. Click **Add to Chart** in the Pine Script Editor
2. The strategy will appear on your chart with the dashboard
3. Open **Strategy Tester** tab to see performance metrics

## ⚙️ Recommended Testing Setup

### Quick Start Configuration

```
📡 Signal Source: "Demo Connector"
🎯 Demo Signal Threshold: 1.0%
🧪 Testing Mode: ON
🚀 Enable Strategy Trades: ON
💰 Position Size: 10%
```

### External Signal Testing

For manual signal testing:
```
📡 Signal Source: "Manual"  
🧪 Testing Mode: ON
📊 Manual/External Signal: 
   - Set to 1 for BUY test
   - Set to -1 for SELL test  
   - Set to 0 for no signal
```

## 🎮 Demo Signal Generator

**Perfect for testing!** The demo connector automatically generates signals:

- **BUY signals**: When price moves **up** by threshold % from previous bar
- **SELL signals**: When price moves **down** by threshold % from previous bar
- **Configurable threshold**: 0.1% to 5.0% (start with 1.0%)
- **No external indicators needed** - fully self-contained

### Recommended Demo Settings:
- **Chart**: Any crypto (BTCUSDT recommended for testing)
- **Timeframe**: 1H or 15M (good signal frequency)
- **Demo Threshold**: 0.5% to 1.0% (more signals for testing)

## 🏷️ Understanding the Label System

Labels **always appear** when signals are detected:

### Label Format: `[Direction] [Filter] [Trade]`
- **Long ✅ 🚀** = Buy signal, filters passed, trade executed
- **Long ❌ ⏸️** = Buy signal, filters failed, no trade  
- **Short ✅ 🚀** = Sell signal, filters passed, trade executed
- **Short ❌ ⏸️** = Sell signal, filters failed, no trade

### What Each Icon Means:
- **✅** = All filter checks passed
- **❌** = One or more filter checks failed
- **🚀** = Trade was executed  
- **⏸️** = Trade was blocked (not executed)

## 📊 Dashboard Understanding

The top-right dashboard shows real-time strategy metrics:

### Current Status Display
- **🔔 Alerts**: ON/OFF
- **📡 Source**: Current signal source (Demo/Manual/External)
- **🧪 Testing**: Testing mode status
- **📊 Trades**: Trade count and current P&L

### Filter Status (Live Updates)
- **✅ Win Rate: PASS (XX.X%)** = Strategy win rate meets threshold
- **❌ Win Rate: FAIL (XX.X%)** = Strategy win rate below threshold
- **✅ Avg Win: PASS (XX.X%)** = Average winning trade meets minimum
- **✅ Max DD: PASS (XX.X%)** = Maximum drawdown within limits

## 🎯 Strategy Settings Explained

### Trade Management
- **Position Size %**: Percentage of equity per trade (default: 10%)
- **TP1/TP2/TP3 Distance**: Take profit levels (1.2%, 2.5%, 5.0%)
- **Stop Loss %**: Stop loss distance from entry (2.0%)
- **TP1/TP2 Exit %**: Partial exit percentages (33% each)

### Filter Settings  
- **TP1 Minimum Profit %**: Required profit threshold (1.2%)
- **TP1 Success Rate %**: Required win rate (90%)
- **Average Drawdown Limit %**: Maximum acceptable drawdown (2.1%)
- **Minimum Trade History**: Trades needed before filtering (50)

### Testing & Development
- **Testing Mode**: Bypass strict filters for development
- **Show Signal Plots**: Display debug data in data window
- **Enable Strategy Trades**: Actually execute trades vs just show labels

## 🧪 Testing Workflow

### Step 1: Basic Functionality Test
1. **Load strategy** on BTCUSDT 1H chart
2. **Set Demo Connector** with 1.0% threshold
3. **Enable Testing Mode**
4. **Look for labels** appearing on price moves
5. **Check dashboard** for live updates

### Step 2: Strategy Execution Test  
1. **Open Strategy Tester** tab
2. **Check "Overview"** for basic performance metrics
3. **Check "List of trades"** for individual trade details
4. **Monitor "Performance"** tab for detailed statistics

### Step 3: Signal Source Testing
1. **Test Demo Mode**: Should auto-generate signals
2. **Test Manual Mode**: Manually set signals to 1/-1
3. **Compare label vs strategy execution**: Should match

## 🔧 Troubleshooting

### Common Issues & Solutions

#### 1. **No Labels Appearing**
- **Cause**: Demo threshold too high or no price movement
- **Solution**: 
  - Lower "Demo Signal Threshold" to 0.5%
  - Switch to more volatile timeframe (15M)
  - Try manual signals (set to 1 or -1)

#### 2. **Labels Show but No Strategy Trades**
- **Cause**: Strategy execution settings
- **Solution**: 
  - Check "Enable Strategy Trades" is ON
  - Verify "Testing Mode" is ON (bypasses strict filters)
  - Look for ❌⏸️ indicators (filters blocking trades)

#### 3. **All Labels Show ❌⏸️ (No Trades)**
- **Cause**: Strict filters blocking all signals  
- **Solution**: 
  - Turn ON "Testing Mode" to bypass filters
  - Lower filter thresholds for testing
  - Check minimum trade history requirement

#### 4. **Dashboard Not Visible**
- **Cause**: Chart scaling or positioning
- **Solution**: 
  - Zoom out to see top-right corner
  - Refresh the strategy indicator
  - Check if overlapping with other indicators

#### 5. **Strategy Tester Shows "No Data"**
- **Cause**: No trades executed yet or data loading
- **Solution**: 
  - Wait for signals to generate trades
  - Check "List of trades" tab instead of "Overview"
  - Ensure strategy is actually executing (🚀 icons)

### Data Window Debugging

Open **Data Window** to see debug values:
- **Signal Direction**: Should show 1, -1, or 0
- **Show Label**: Should show 1 when labels appear
- **Execute Trade**: Should show 1 when trades execute
- **Position Size**: Shows current strategy position

## 📈 Performance Expectations

### Demo Mode Results (1H BTCUSDT)
- **Signal Frequency**: 2-5 signals per day (1.0% threshold)
- **Label Accuracy**: 100% (all signals show labels)
- **Trade Execution**: Depends on filter settings
- **Dashboard Updates**: Real-time with each completed trade

### Filter Behavior
- **Testing Mode ON**: Most/all signals execute (bypass filters)
- **Testing Mode OFF**: Only high-quality signals execute
- **Filter Strictness**: Increases as trade history builds

## 📚 Next Steps

### For Users
1. **Test thoroughly** with demo mode on different timeframes
2. **Understand the filter system** by watching pass/fail patterns
3. **Monitor strategy performance** using built-in metrics
4. **Experiment with settings** to understand impact

### For Developers  
1. **Study the codebase** structure and modular architecture
2. **Contribute to Phase 2** statistical analysis development
3. **Test on multiple assets** to validate cross-asset compatibility
4. **Suggest improvements** via GitHub Issues

## 🆘 Need Help?

- **Issues**: [GitHub Issues](https://github.com/andreoutberg/ao-optimiser-tradingview/issues)
- **Discussions**: [GitHub Discussions](https://github.com/andreoutberg/ao-optimiser-tradingview/discussions)
- **Development**: Contributing to Phase 2 statistical analysis

---

**✅ Current Status**: Phase 1 strategy framework is complete and functional! The core engine works, labels display properly, and the foundation is ready for Phase 2 statistical enhancement.

**🚀 Next Phase**: Advanced statistical analysis and optimization of the filtering system using real backtest data from the strategy execution.
