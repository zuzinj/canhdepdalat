# TradingView EA User Guide - Ichimoku Multi-Kijun Strategy

## Introduction

This Expert Advisor (EA) is built on the Ichimoku system with additional Kijun lines and SMMA indicators to create a multi-timeframe trading system.

## Main Components

### 1. Basic Ichimoku (9, 26, 52, 26)

- **Tenkan-sen (Conversion Line)**: 9-period conversion line (red)
- **Kijun-sen (Base Line)**: 26-period base line (blue)
- **Senkou Span A & B**: Forms the Kumo cloud (green/red)
- **Chikou Span**: 26-period lagging span (purple)

### 2. Additional Kijun Lines

- **Kijun 65**: Black - 65 periods
- **Kijun 129**: Blue - 129 periods
- **Kijun 172**: Green - 172 periods
- **Kijun 234**: Orange - 234 periods

### 3. SMMA Lines (Smoothed Moving Average)

- **SMMA 52**: Magenta - 52 periods
- **SMMA 139**: Cyan - 139 periods
- **SMMA 400**: Yellow - 400 periods

## Installation Guide

### Step 1: Open TradingView
1. Go to https://www.tradingview.com
2. Log in to your account

### Step 2: Open Pine Editor
1. Click "Pine Editor" at the bottom of the screen
2. Click "New" to create a new script

### Step 3: Copy Code
1. Open the `tradingview_ea.pine` file
2. Copy all content
3. Paste into Pine Editor

### Step 4: Save and Add to Chart
1. Click "Save" and name your script
2. Click "Add to Chart" to apply to the chart

## Trading Signals

### Long (Buy) Signal
- ✅ Tenkan-sen crosses above Kijun-sen
- ✅ Price is above the Kumo cloud
- 🔺 Green arrow appears below candle

### Short (Sell) Signal
- ❌ Tenkan-sen crosses below Kijun-sen
- ❌ Price is below the Kumo cloud
- 🔻 Red arrow appears above candle

## Risk Management

### Stop Loss
- Default: 2% from entry price
- Adjustable in Settings

### Take Profit
- Default: 4% from entry price
- Adjustable in Settings

## How to Use

### 1. Trend Analysis
- Observe price position relative to Kumo cloud
- Green cloud: Strong uptrend
- Red cloud: Strong downtrend

### 2. Signal Confirmation
- Check additional Kijun lines to confirm trend
- SMMA lines help identify long-term trends

### 3. Entry Execution
- Wait for system signals (green/red arrows)
- Check volume and other factors
- Enter when all conditions are met

## Customization

### In Strategy Settings:

#### Ichimoku Basic
- Adjust Tenkan, Kijun, Senkou Span B periods
- Change displacement

#### Additional Kijun
- Customize additional Kijun periods (65, 129, 172, 234)

#### SMMA
- Adjust SMMA periods (52, 139, 400)

#### Risk Management
- Enable/disable Stop Loss and Take Profit
- Adjust Stop Loss and Take Profit percentages

#### Trading
- Enable/disable Long or Short trades

## Important Notes

⚠️ **Warning**: 
- This EA is for reference only
- Always test on a demo account first
- Do not use all capital on a single trade
- Trading involves risk, only use capital you can afford to lose

## Backtesting

1. Open Strategy Tester in TradingView
2. Select timeframe and period to test
3. View results:
   - Net Profit
   - Win Rate
   - Max Drawdown
   - Profit Factor

## Features

### Multi-Timeframe Analysis
The system combines multiple timeframes through:
- Basic Ichimoku for short-term signals
- Additional Kijun lines (65, 129, 172, 234) for medium-term trends
- SMMA lines (52, 139, 400) for long-term trends

### Visualization
- Color-coded lines for easy identification
- Cloud fill shows trend direction
- Clear buy/sell signals with arrows
- All indicators on one chart

## Strategy Logic

### Entry Conditions
**Long Entry:**
1. Tenkan-sen crosses above Kijun-sen (bullish crossover)
2. Price must be above both Senkou Span A and B (above the cloud)

**Short Entry:**
1. Tenkan-sen crosses below Kijun-sen (bearish crossover)
2. Price must be below both Senkou Span A and B (below the cloud)

### Exit Conditions
- Automatic exit via Stop Loss (default 2%)
- Automatic exit via Take Profit (default 4%)
- Manual exit based on opposite signal

## Best Practices

1. **Use Multiple Timeframes**: Check higher timeframes for overall trend
2. **Confirm with Volume**: Higher volume on signals increases reliability
3. **Respect the Cloud**: Strong support/resistance zone
4. **Use Additional Kijun Lines**: For trend confirmation and dynamic support/resistance
5. **Follow SMMA**: For overall market direction

## Support

If you have questions or need support, please create an issue on the GitHub repository.

## Version Information

- **Version**: 1.0
- **Pine Script**: Version 5
- **Created**: 2025-12-27

## Author

Repository: https://github.com/zuzinj/canhdepdalat

## License

This code is provided as-is for educational and research purposes.
