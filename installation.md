# AO Optimiser v0.8.0 - Installation Guide

✅ **Current Status**: Phase 2 (Dual Mode System) complete and functional! 

This guide will help you install and test the AO Optimiser **strategy** v0.8.0 with the new dual-mode filtering system.

## 🆕 **What's New in v0.8.0**

### **Dual Mode System:**
- **⚡ Optimised Mode**: Fully automated - calculates TP/SL levels and validates profitability
- **🎯 Custom Mode**: Manual control over filter thresholds with historical validation

### **Simplified Configuration:**
- Position size: Fixed at 2% (adjustable in Properties tab)
- Signal validation: Always strict 
- Historical tracking: Always enabled
- No manual toggles - streamlined for production use

## 📋 Prerequisites

- TradingView account (Free or Paid)
- Basic understanding of Pine Script strategies
- External trading indicator (optional - demo mode available)

## 🚀 Strategy Installation

### Step 1: Download the Strategy Code
1. Go to [`src/ao_optimiser.pine`](../src/ao_optimiser.pine)
2. Copy the complete strategy code (v0.8.0)

### Step 2: Add to TradingView
1. Open [TradingView](https://www.tradingview.com/)
2. Go to **Pine Script Editor** (bottom panel)
3. Create a **New Strategy** (⚠️ Important: NOT indicator!)
4. **Delete** the default code
5. **Paste** the AO Optimiser v0.8.0 strategy code
6. Click **Save** and name it "AO Optimiser v0.8.0"

### Step 3: Add to Chart and Configure
1. Click **Add to Chart** in the Pine Script Editor
2. The strategy will appear on your chart with the mode-specific dashboard
3. Open **Strategy Tester** tab to see performance metrics

## ⚙️ **Mode Selection & Configuration**

### 🎯 **Optimised Mode** (Recommended for experienced users)

**Perfect for:** Production deployment, watchlist scanning, hands-off operation
