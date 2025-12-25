# TradingView Expert Advisor (EA)

This repository contains a complete TradingView Expert Advisor (EA) implementation using Pine Script v5.

## 📁 Directory Structure

```
tradingview/
├── indicators/
│   └── moving_average_crossover.pine    # Basic MA crossover indicator
└── strategies/
    └── ma_crossover_ea.pine              # Full Expert Advisor with risk management
```

## 📊 Strategy Overview

The **Moving Average Crossover EA** is a trend-following strategy that generates trading signals based on the crossover of two moving averages (fast and slow).

### Features

- ✅ **Multiple MA Types**: Support for SMA and EMA
- ✅ **Risk Management**: Configurable stop loss and take profit
- ✅ **Position Sizing**: Percentage-based position sizing
- ✅ **Session Filter**: Optional trading session time filter
- ✅ **Alert System**: Built-in alert conditions for entry/exit signals
- ✅ **Visual Indicators**: Clear buy/sell signals with stop loss and take profit levels displayed

## 🚀 How to Use

### 1. Import the Strategy to TradingView

1. Open [TradingView](https://www.tradingview.com/)
2. Click on "Pine Editor" at the bottom of the chart
3. Create a new script
4. Copy the contents of `tradingview/strategies/ma_crossover_ea.pine`
5. Paste it into the Pine Editor
6. Click "Add to Chart"

### 2. Configure Strategy Parameters

#### Moving Average Settings
- **Fast MA Length**: Period for the fast moving average (default: 9)
- **Slow MA Length**: Period for the slow moving average (default: 21)
- **MA Type**: Choose between SMA (Simple) or EMA (Exponential)

#### Risk Management
- **Use Stop Loss**: Enable/disable stop loss (default: enabled)
- **Stop Loss %**: Percentage stop loss from entry price (default: 2%)
- **Use Take Profit**: Enable/disable take profit (default: enabled)
- **Take Profit %**: Percentage take profit from entry price (default: 4%)

#### Position Sizing
- **Risk Per Trade**: Percentage of equity to risk per trade (default: 10%)

#### Session Filter
- **Use Trading Session Filter**: Enable/disable session filter (default: disabled)
- **Trading Session**: Specific trading hours (default: 09:30-16:00)

### 3. Set Up Alerts

1. Right-click on the chart
2. Select "Add Alert"
3. Choose the strategy and alert condition:
   - Long Entry Alert
   - Short Entry Alert
   - Exit Long Alert
   - Exit Short Alert
4. Configure notification method (email, SMS, webhook, etc.)

## 📈 Trading Logic

### Entry Signals

**Long Entry (Buy)**:
- Fast MA crosses above Slow MA
- Fast MA > Slow MA (confirming uptrend)
- Within trading session (if filter enabled)

**Short Entry (Sell)**:
- Fast MA crosses below Slow MA
- Fast MA < Slow MA (confirming downtrend)
- Within trading session (if filter enabled)

### Exit Signals

**Exit Long Position**:
- Stop loss hit (price drops by configured %)
- Take profit hit (price rises by configured %)
- Bearish crossover (Fast MA crosses below Slow MA)

**Exit Short Position**:
- Stop loss hit (price rises by configured %)
- Take profit hit (price drops by configured %)
- Bullish crossover (Fast MA crosses above Slow MA)

## 🎯 Backtesting

The strategy includes built-in backtesting capabilities:

1. Open the "Strategy Tester" tab at the bottom of TradingView
2. Review performance metrics:
   - Net Profit
   - Win Rate
   - Profit Factor
   - Maximum Drawdown
   - Sharpe Ratio
3. Optimize parameters using the "Strategy Tester" settings
4. Review trade list for detailed entry/exit points

## ⚙️ Recommended Settings

### For Day Trading (Intraday)
- Fast MA: 9
- Slow MA: 21
- Timeframe: 5m or 15m
- Stop Loss: 1-2%
- Take Profit: 2-3%
- Session Filter: Enabled

### For Swing Trading
- Fast MA: 20
- Slow MA: 50
- Timeframe: 1h or 4h
- Stop Loss: 3-5%
- Take Profit: 6-10%
- Session Filter: Disabled

### For Position Trading
- Fast MA: 50
- Slow MA: 200
- Timeframe: 1D
- Stop Loss: 5-10%
- Take Profit: 15-20%
- Session Filter: Disabled

## 🔧 Customization

You can customize the strategy by modifying:

1. **Entry Conditions**: Add additional filters (RSI, volume, etc.)
2. **Exit Conditions**: Implement trailing stops or time-based exits
3. **Risk Management**: Add ATR-based stop loss or dynamic position sizing
4. **Indicators**: Combine with other technical indicators

Example of adding RSI filter:
```pine
// Add RSI indicator
rsiLength = input.int(14, title="RSI Length")
rsiValue = ta.rsi(close, rsiLength)

// Modify entry conditions
longCondition = bullishCross and fastMA > slowMA and rsiValue < 70 and inSession
shortCondition = bearishCross and fastMA < slowMA and rsiValue > 30 and inSession
```

## 📝 Important Notes

- **Backtesting**: Always backtest on historical data before live trading
- **Commission & Slippage**: Strategy includes 0.1% commission and 2 ticks slippage
- **Risk Warning**: Past performance does not guarantee future results
- **Capital Management**: Never risk more than you can afford to lose
- **Market Conditions**: This strategy works best in trending markets

## 📚 Resources

- [TradingView Pine Script Documentation](https://www.tradingview.com/pine-script-docs/)
- [Pine Script v5 User Manual](https://www.tradingview.com/pine-script-docs/en/v5/Introduction.html)
- [TradingView Community Scripts](https://www.tradingview.com/scripts/)

## 🤝 Contributing

Feel free to fork this repository and submit improvements or additional strategies.

## ⚖️ License

This strategy is provided for educational purposes. Use at your own risk.

## 📧 Support

For questions or issues, please open an issue on GitHub.

---

**Disclaimer**: Trading involves substantial risk. This EA is for educational purposes only and should not be considered financial advice. Always do your own research and consider consulting with a financial advisor before trading.
