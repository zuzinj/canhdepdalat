# TradingView EA - Cảnh Đẹp Đà Lạt

## 📁 Files Overview

This repository contains a complete TradingView trading system:

1. **indicator.pine** - Technical indicator for market analysis
2. **strategy_ea.pine** - Expert Advisor (EA/Strategy) for automated trading
3. **HUONG_DAN.md** - Vietnamese documentation
4. **README.md** - This file

## 🎯 Features

### Indicator Features:
- **Moving Average Crossover** (Fast MA & Slow MA)
- **RSI (Relative Strength Index)** with overbought/oversold levels
- **MACD** (Moving Average Convergence Divergence)
- Visual buy/sell signals on chart
- Background color based on trend
- Alert conditions for notifications

### Strategy EA Features:
All indicator features PLUS:
- **Automated Trading** - Execute trades based on signals
- **Risk Management**:
  - Stop Loss (configurable %)
  - Take Profit (configurable %)
  - Trailing Stop (optional)
- **Position Sizing** - Configurable risk per trade
- **Time Filter** - Trade only during specific hours
- **Position Dashboard** - Real-time P/L and position info
- **Multiple Alert Types** - Entry and exit notifications
- **Backtesting** - Test on historical data

## 🚀 Quick Start

### 1. Install the Indicator

1. Open [TradingView](https://www.tradingview.com/)
2. Open **Pine Editor** (bottom of screen)
3. Copy contents of `indicator.pine`
4. Paste into Pine Editor
5. Click **"Save"** and name your indicator
6. Click **"Add to Chart"**

### 2. Install the Strategy EA

1. Open TradingView
2. Open **Pine Editor**
3. Copy contents of `strategy_ea.pine`
4. Paste into Pine Editor
5. Click **"Save"** and name your strategy
6. Click **"Add to Chart"**

## 📊 Trading Logic

### LONG Entry Signal (BUY)
Conditions for opening a long position:
- ✅ Fast MA crosses above Slow MA
- ✅ RSI < 70 (not overbought)
- ✅ MACD Line > Signal Line with positive histogram

### SHORT Entry Signal (SELL)
Conditions for opening a short position:
- ✅ Fast MA crosses below Slow MA
- ✅ RSI > 30 (not oversold)
- ✅ MACD Line < Signal Line with negative histogram

### Exit Conditions

**Exit LONG:**
- Fast MA crosses below Slow MA, OR
- RSI > 70 (overbought), OR
- MACD crosses below Signal Line

**Exit SHORT:**
- Fast MA crosses above Slow MA, OR
- RSI < 30 (oversold), OR
- MACD crosses above Signal Line

## ⚙️ Configuration Parameters

### Moving Average
- **Fast MA Length**: 9 (default)
- **Slow MA Length**: 21 (default)
- **MA Type**: EMA or SMA

### RSI
- **RSI Length**: 14 (default)
- **Overbought**: 70 (default)
- **Oversold**: 30 (default)

### MACD
- **Fast**: 12 (default)
- **Slow**: 26 (default)
- **Signal**: 9 (default)

### Risk Management (Strategy EA only)
- **Stop Loss %**: 2% (default)
- **Take Profit %**: 4% (default)
- **Trailing Stop %**: 1.5% (default)
- **Risk Per Trade**: 100% of equity (adjustable)

## 🔔 Setting Up Alerts

### For Indicator:
1. Right-click on indicator on chart
2. Select **"Add Alert"**
3. Choose condition (Buy/Sell Alert)

### For Strategy EA:
1. Click Alert icon (⏰) on toolbar
2. Choose condition:
   - Long Entry Alert
   - Short Entry Alert
   - Long Exit Alert
   - Short Exit Alert

## 📈 Chart Display

### Indicator Shows:
- 📈 Blue line: Fast MA
- 📈 Red line: Slow MA
- ▲ Green arrow up: Buy signal
- ▼ Red arrow down: Sell signal
- 🟢 Light green background: Uptrend
- 🔴 Light red background: Downtrend

### Strategy EA Shows Additionally:
- All indicator elements
- 📊 Position info table (top right):
  - Position status (LONG/SHORT/NONE)
  - Entry price
  - Position size
  - Unrealized P/L
  - Total P/L
- 🔴 Red Stop Loss line
- 🟢 Green Take Profit line

## 🔧 Customization

To customize with your own indicator logic:

1. Open `strategy_ea.pine` in Pine Editor
2. Find **"INDICATOR CALCULATIONS"** section
3. Add or replace indicator calculations
4. Update **"SIGNAL CONDITIONS"** section with your logic
5. Test and adjust parameters

Example adding Bollinger Bands:

```pine
// Add Bollinger Bands
bbLength = input.int(20, "BB Length")
bbMult = input.float(2.0, "BB Multiplier")
[bbMiddle, bbUpper, bbLower] = ta.bb(close, bbLength, bbMult)

// Update entry conditions
longCondition = bullishCrossover and rsi < 70 and macdBullish and close < bbLower
shortCondition = bearishCrossover and rsi > 30 and macdBearish and close > bbUpper
```

## 💡 Important Notes

1. **Backtest First**: Always test on historical data before live trading
2. **Adjust Parameters**: Each market/pair needs different settings
3. **Risk Management**: Never risk more than 1-2% per trade
4. **Monitor Regularly**: EA doesn't replace human oversight
5. **Market Conditions**: Works best in trending markets

## 🛠️ Technical Details

- **Pine Script Version**: v5
- **Initial Capital**: $10,000 (default)
- **Position Sizing**: Percent of equity
- **Commission**: 0.1% per trade
- **Slippage**: 3 ticks

## ⚠️ Disclaimer

- This is a trading tool, not investment advice
- Always do your own research
- Trading involves risk of capital loss
- Past performance doesn't guarantee future results

## 📝 Version History

### Version 1.0 (2025-12-25)
- ✅ Created base indicator with MA, RSI, MACD
- ✅ Converted to Strategy EA
- ✅ Added risk management (Stop Loss, Take Profit, Trailing Stop)
- ✅ Added time filter for trading hours
- ✅ Added position info dashboard
- ✅ Set up alerts for all signals

## 📚 Resources

- [TradingView](https://www.tradingview.com/)
- [Pine Script Documentation](https://www.tradingview.com/pine-script-docs/)
- [Vietnamese Guide](HUONG_DAN.md) - Hướng dẫn tiếng Việt

---

**Happy Trading! 🚀📈**
