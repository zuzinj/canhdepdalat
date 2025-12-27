# Quick Reference Guide / Hướng Dẫn Nhanh

## 🚀 Quick Start / Bắt Đầu Nhanh

### 1. Copy Code to TradingView
```
1. Open TradingView → Pine Editor
2. Copy code from tradingview_ea.pine
3. Paste → Save → Add to Chart
```

### 2. Default Settings
- ✅ All indicators enabled
- ✅ Stop Loss: 2%
- ✅ Take Profit: 4%
- ✅ Long & Short trades enabled

## 📊 Quick Signal Guide / Hướng Dẫn Tín Hiệu Nhanh

### BUY (LONG) 🔺
```
✓ Green arrow appears below candle
✓ Tenkan crosses above Kijun
✓ Price above cloud
```

### SELL (SHORT) 🔻
```
✓ Red arrow appears above candle
✓ Tenkan crosses below Kijun
✓ Price below cloud
```

## 🎯 Trading Rules / Quy Tắc Giao Dịch

### Entry Rules
1. **Wait for signal arrow** (green/red)
2. **Check higher timeframe** for trend confirmation
3. **Enter on next candle** after signal
4. **Set Stop Loss** at -2% (automatic)
5. **Set Take Profit** at +4% (automatic)

### Exit Rules
1. **Automatic exit** at Stop Loss or Take Profit
2. **Manual exit** if opposite signal appears
3. **Trailing stop** if strong trend continues

## 🔧 Settings Optimization / Tối Ưu Cài Đặt

### For Scalping (1-15 min)
```
Ichimoku: Keep default (9, 26, 52, 26)
Stop Loss: 1-2%
Take Profit: 2-3%
```

### For Day Trading (15min-4h)
```
Ichimoku: Keep default (9, 26, 52, 26)
Stop Loss: 2-3%
Take Profit: 4-6%
```

### For Swing Trading (4h-1D)
```
Ichimoku: Keep default (9, 26, 52, 26)
Stop Loss: 3-5%
Take Profit: 8-12%
```

## 📈 Indicator Explanation / Giải Thích Chỉ Báo

### Basic Ichimoku
| Line | Period | Color | Purpose |
|------|--------|-------|---------|
| Tenkan | 9 | Red | Fast signal |
| Kijun | 26 | Blue | Base line |
| Cloud | 26+52 | Green/Red | Support/Resistance |

### Additional Kijun
| Line | Period | Color | Purpose |
|------|--------|-------|---------|
| Kijun 65 | 65 | Black | Quarter support |
| Kijun 129 | 129 | Blue | Half support |
| Kijun 172 | 172 | Green | 2/3 support |
| Kijun 234 | 234 | Orange | Fibonacci support |

### SMMA Lines
| Line | Period | Color | Purpose |
|------|--------|-------|---------|
| SMMA 52 | 52 | Magenta | Short trend |
| SMMA 139 | 139 | Cyan | Medium trend |
| SMMA 400 | 400 | Yellow | Long trend |

## 💡 Pro Tips / Mẹo Chuyên Nghiệp

### 1. Trend Confirmation
- ✅ Price above SMMA 400 = Strong uptrend
- ✅ Price below SMMA 400 = Strong downtrend
- ⚠️ Price near SMMA 400 = Wait for breakout

### 2. Entry Timing
- ✅ Best: Signal + Volume spike
- ✅ Good: Signal + Multiple timeframe alignment
- ⚠️ Risky: Signal alone without confirmation

### 3. Risk Management
- Never risk more than 1-2% per trade
- Always use Stop Loss
- Don't move Stop Loss against position
- Take partial profits at 2% if nervous

### 4. Multiple Timeframe Strategy
```
Step 1: Check 1D chart for overall trend
Step 2: Check 4H chart for intermediate trend
Step 3: Check 1H chart for entry timing
Step 4: Enter on 15m or 5m when signal appears
```

## ⚠️ Common Mistakes / Lỗi Thường Gặp

### ❌ DON'T DO THIS:
1. Trading against higher timeframe trend
2. Ignoring Stop Loss signals
3. Over-leveraging positions
4. Trading during low volume periods
5. Moving Stop Loss to avoid losses

### ✅ DO THIS INSTEAD:
1. Trade with the trend
2. Always respect Stop Loss
3. Use proper position sizing (1-2% risk)
4. Trade during active market hours
5. Accept losses and move on

## 📱 Quick Checklist / Danh Sách Kiểm Tra

### Before Opening Trade
- [ ] Signal arrow appeared?
- [ ] Higher timeframe confirms?
- [ ] Stop Loss set?
- [ ] Take Profit set?
- [ ] Position size calculated?
- [ ] Risk acceptable (1-2%)?

### After Opening Trade
- [ ] Entry price noted?
- [ ] Stop Loss order placed?
- [ ] Take Profit order placed?
- [ ] Trade logged?

### After Closing Trade
- [ ] Profit/Loss recorded?
- [ ] What went right/wrong?
- [ ] Lesson learned?

## 🆘 Troubleshooting / Xử Lý Sự Cố

### No signals appearing?
- Check if script is running (green dot)
- Increase chart timeframe
- Wait for volatility

### Too many false signals?
- Increase timeframe
- Add volume filter
- Trade only with trend

### Signals not matching manual analysis?
- EA is systematic, not discretionary
- Trust the system or adjust parameters
- Backtest to verify

## 📞 Support / Hỗ Trợ

- 📖 Full Guide: [HUONG_DAN.md](HUONG_DAN.md)
- 📖 English Guide: [README_EN.md](README_EN.md)
- 📊 Structure: [STRUCTURE.md](STRUCTURE.md)
- 🐛 Issues: Create issue on GitHub

## 🎓 Learning Resources / Tài Nguyên Học Tập

### Recommended Study Topics:
1. Ichimoku Cloud basics
2. Support and Resistance
3. Risk Management
4. Position Sizing
5. Trading Psychology

### Practice Steps:
1. Demo trade for 1 month
2. Review all trades
3. Adjust strategy
4. Demo trade 1 more month
5. Start with small real capital

---

**Remember**: 
- 📉 No strategy wins 100% of the time
- 💰 Risk management is more important than entries
- 📊 Consistency beats perfection
- 🎯 Focus on process, not results

**Good luck trading! / Chúc may mắn trong giao dịch!** 🚀
