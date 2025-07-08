# AO Optimiser - Installation Guide

⚠️ **Development Status**: This project is currently in initial development phase. No stable release is available yet.

This guide will help you set up the AO Optimiser indicator for development and testing purposes.

## 📋 Prerequisites

- TradingView account (Free or Paid)
- Basic understanding of Pine Script indicators
- External trading indicator that outputs standardized signals (for testing)
- Discord webhook (optional, for future alert testing)

## 🚧 Development Installation

### Step 1: Get the Current Code
1. Go to the repository: [https://github.com/andreoutberg/ao-optimiser-tradingview](https://github.com/andreoutberg/ao-optimiser-tradingview)
2. Navigate to `src/ao_optimiser.pine`
3. Copy the Pine Script code

### Step 2: Add to TradingView
1. Open [TradingView](https://www.tradingview.com/)
2. Go to **Pine Script Editor** (bottom panel)
3. Create a **New Indicator**
4. **Delete** the default code
5. **Paste** the AO Optimiser code
6. Click **Save** and name it "AO Optimiser - Dev"

### Step 3: Add to Chart
1. Click **Add to Chart** in the Pine Script Editor
2. The indicator will appear on your chart
3. Configure the settings for testing

## ⚙️ Current Configuration Options

### Available Settings (Phase 1)

```
Filter Settings (Basic Implementation):
├── TP1 Minimum Profit %: 1.2
├── TP1 Success Rate %: 90  
├── Average Drawdown Limit %: 2.1
├── Minimum Trade History: 50
└── Confidence Threshold %: 85

Operational Settings:
├── Entry Offset %: 0.1
├── Cooldown Period (bars): 24
├── Enable Alerts: true
└── Max Alerts per Hour: 5
```

### External Signal Testing

**For Development Testing**: You can manually test signals using the External Signal input:

1. Open the AO Optimiser settings
2. Find **"External Signal"** input
3. Test with different values:
   - Enter `1` for BUY signal test
   - Enter `-1` for SELL signal test
   - Enter `0` for no signal

**For External Indicator Connection** (when available):
Your external indicator needs a plot like this:
```pine
plot(your_buy_condition ? 1 : your_sell_condition ? -1 : 0, "Signal", display=display.data_window)
```

## 📊 Current Dashboard Features

### What Works Now (Phase 1)
- Basic dashboard display in top-right corner
- Simple pass/fail indicators for:
  - TP Success Rate
  - TP1 Minimum Profit (placeholder)
  - Average Drawdown
- Alert ON/OFF status

### What's Coming (Future Phases)
- Real-time performance metrics
- Enhanced visual indicators
- Detailed trading statistics
- Advanced filtering system

## 🚨 Alert System Status

### Current Implementation
- Basic alert functionality
- Simple text-based alerts
- Manual signal testing capability

### Coming Soon (Phase 4)
- Discord webhook integration
- Color-coded embed formatting
- Advanced alert customization
- Proper cooldown mechanisms

## 🔧 Development Notes

### Known Limitations
- **Phase 1 Development**: Many features are placeholders
- **No Historical Analysis**: Statistical calculations not yet implemented
- **Basic Filtering**: Advanced filter logic pending
- **Limited Dashboard**: Full metrics display coming in Phase 3

### Testing Recommendations
1. **Manual Signal Testing**: Use the External Signal input to test basic functionality
2. **Chart Observation**: Monitor dashboard updates and basic signal processing
3. **Performance Monitoring**: Check for any Pine Script errors or timeouts
4. **Settings Experimentation**: Try different threshold values

## 🐛 Troubleshooting

### Common Issues

#### 1. **Indicator Not Loading**
- **Cause**: Pine Script syntax errors
- **Solution**: 
  - Check Pine Script console for error messages
  - Ensure you copied the complete code
  - Refresh the chart and try again

#### 2. **No Dashboard Visible**
- **Cause**: Chart scaling or positioning
- **Solution**: 
  - Zoom out on the chart
  - Check the top-right area of the chart
  - Refresh the indicator

#### 3. **External Signal Not Working**
- **Cause**: No external indicator connected
- **Solution**: 
  - Use manual testing with input values
  - Verify external indicator outputs correct format
  - Check signal_direction plot in data window

#### 4. **All Checks Show FAIL**
- **Cause**: Normal for development phase - not enough data
- **Solution**: 
  - This is expected behavior
  - Lower "Minimum Trade History" for testing
  - Wait for more development progress

### Development Testing
- Use **Pine Script Console** to check for errors
- Monitor **Data Window** for signal plots
- Test with **different timeframes** for compatibility
- Check **resource usage** for performance

## 📚 Next Steps for Developers

### Contributing to Development
1. **Fork the Repository**: Create your own copy for modifications
2. **Test Changes**: Verify functionality across different assets
3. **Document Issues**: Report bugs or enhancement ideas
4. **Submit Pull Requests**: Contribute improvements back to the project

### Development Roadmap Participation
- **Phase 1**: Help complete core engine functionality
- **Phase 2**: Contribute to statistical analysis implementation
- **Phase 3**: Assist with dashboard and filtering development
- **Phase 4**: Support alert system and Discord integration
- **Phase 5**: Participate in testing and optimization

## 🆘 Support & Development Community

- **Issues**: [GitHub Issues](https://github.com/andreoutberg/ao-optimiser-tradingview/issues)
- **Discussions**: [GitHub Discussions](https://github.com/andreoutberg/ao-optimiser-tradingview/discussions)
- **Development Updates**: Watch the repository for progress updates

---

**⚠️ Important**: 
- This is development software - expect bugs and incomplete features
- Not suitable for live trading yet
- Use only for testing and development purposes
- No stable release available - code changes frequently

**🔮 Future**: Once development reaches a stable state, proper installation packages and documentation will be provided.
