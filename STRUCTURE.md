# Cấu Trúc Indicators / Indicator Structure

## Visualization of the EA Components

```
┌─────────────────────────────────────────────────────────────────┐
│                   TRADINGVIEW CHART                              │
│                                                                   │
│  ▲                                                                │
│  │                                                                │
│  │     SMMA 400 ═══════════════════════════════ (Yellow)         │
│  │                                                                │
│  │     Kijun 234 ────────────────────────────── (Orange)         │
│  │                                                                │
│  │     Kijun 172 ────────────────────────────── (Green)          │
│  │                                                                │
│  │     SMMA 139 ═══════════════════════════════ (Cyan)           │
│  │                                                                │
│  │     Kijun 129 ────────────────────────────── (Blue)           │
│  │                                                                │
│  │     Kijun 65  ────────────────────────────── (Black)          │
│  │                                                                │
│  │     SMMA 52   ═══════════════════════════════ (Magenta)       │
│  │                                                                │
│  │     ┌──── Senkou Span B (52) ────┐                            │
│  │     │    ░░░░░ KUMO CLOUD ░░░░░   │                           │
│  │     └──── Senkou Span A (9+26)/2 ─┘                           │
│  │                                                                │
│  │     Tenkan-sen (9)  ──────────────────────── (Red)            │
│  │     Kijun-sen (26)  ──────────────────────── (Blue)           │
│  │                                                                │
│  │     PRICE ACTION  ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓                    │
│  │                                                                │
│  │     🔺 Buy Signal    🔻 Sell Signal                           │
│  │                                                                │
│  │     Chikou Span (26 periods back) ──────────  (Purple)        │
│  │                                                                │
│  └────────────────────────────────────────────────────> Time     │
└─────────────────────────────────────────────────────────────────┘
```

## Thành Phần Hệ Thống / System Components

### 1. ICHIMOKU BASIC (Short-term)
- **Tenkan-sen (9)**: Fast conversion line
- **Kijun-sen (26)**: Base line
- **Senkou Span A**: (Tenkan + Kijun) / 2
- **Senkou Span B (52)**: 52-period midpoint
- **Chikou Span**: Lagging line (26 periods back)

### 2. ADDITIONAL KIJUN (Medium-term)
- **Kijun 65**: Quarter-year cycle
- **Kijun 129**: Half-year cycle
- **Kijun 172**: 2/3-year cycle
- **Kijun 234**: Fibonacci-based cycle

### 3. SMMA LINES (Long-term)
- **SMMA 52**: Weekly cycle
- **SMMA 139**: Monthly cycle
- **SMMA 400**: Yearly trend

## Tín Hiệu Giao Dịch / Trading Signals

### Long Signal (Buy) 🔺
```
Conditions:
1. Tenkan-sen crosses ABOVE Kijun-sen
2. Price is ABOVE the Kumo cloud
3. (Optional) Chikou Span is ABOVE price 26 periods ago

Result: Green arrow below candle
```

### Short Signal (Sell) 🔻
```
Conditions:
1. Tenkan-sen crosses BELOW Kijun-sen
2. Price is BELOW the Kumo cloud
3. (Optional) Chikou Span is BELOW price 26 periods ago

Result: Red arrow above candle
```

## Cách Đọc Biểu Đồ / How to Read the Chart

### Trend Direction
- **Price above cloud** = Uptrend (Bullish)
- **Price below cloud** = Downtrend (Bearish)
- **Price in cloud** = Ranging/Consolidation

### Support & Resistance
- **Kijun lines** act as dynamic support/resistance
- **SMMA lines** show major support/resistance zones
- **Cloud edges** are strong support/resistance areas

### Multiple Timeframe Confirmation
1. **Short-term**: Basic Ichimoku (9, 26, 52)
2. **Medium-term**: Additional Kijun (65, 129, 172, 234)
3. **Long-term**: SMMA (52, 139, 400)

## Example Trade Scenarios

### Scenario 1: Strong Bullish Setup
```
✓ Price above all indicators
✓ All indicators trending upward
✓ Tenkan > Kijun
✓ Green cloud ahead
→ STRONG BUY signal
```

### Scenario 2: Strong Bearish Setup
```
✓ Price below all indicators
✓ All indicators trending downward
✓ Tenkan < Kijun
✓ Red cloud ahead
→ STRONG SELL signal
```

### Scenario 3: Consolidation
```
✓ Price in cloud
✓ Indicators crossing frequently
✓ Mixed signals
→ WAIT for breakout
```

## Risk Management Levels

```
Entry: When signal appears
Stop Loss: -2% from entry (default)
Take Profit: +4% from entry (default)

Risk:Reward = 1:2
```

## Best Timeframes

- **Scalping**: 1m, 5m, 15m
- **Day Trading**: 15m, 30m, 1h
- **Swing Trading**: 4h, 1D
- **Position Trading**: 1D, 1W

## Color Legend

| Indicator | Color | Purpose |
|-----------|-------|---------|
| Tenkan-sen | Red | Fast trend |
| Kijun-sen | Blue | Medium trend |
| Senkou Span A | Green/Red | Cloud leading edge |
| Senkou Span B | Green/Red | Cloud slow edge |
| Chikou Span | Purple | Price confirmation |
| Kijun 65 | Black | Quarter cycle |
| Kijun 129 | Blue | Half cycle |
| Kijun 172 | Green | 2/3 cycle |
| Kijun 234 | Orange | Fibonacci cycle |
| SMMA 52 | Magenta | Short SMMA |
| SMMA 139 | Cyan | Medium SMMA |
| SMMA 400 | Yellow | Long SMMA |
