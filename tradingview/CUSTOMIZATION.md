# Hướng Dẫn Tùy Chỉnh EA - Customization Guide

## 📝 Cách Thêm Chỉ Báo Riêng / How to Add Your Own Indicators

### Bước 1: Xác định chỉ báo của bạn / Step 1: Identify Your Indicator

Trước tiên, bạn cần biết:
1. Công thức tính toán chỉ báo
2. Các thông số đầu vào (input parameters)
3. Điều kiện tín hiệu mua/bán

First, you need to know:
1. The indicator calculation formula
2. Input parameters
3. Buy/sell signal conditions

### Bước 2: Thêm Input Parameters / Step 2: Add Input Parameters

Mở file `strategy_ea.pine` và thêm thông số của bạn vào phần **INPUT PARAMETERS**:

```pine
// === Your Indicator Settings ===
yourParam1 = input.int(20, "Your Parameter 1", minval=1, group="Your Indicator")
yourParam2 = input.float(2.0, "Your Parameter 2", minval=0.1, group="Your Indicator")
yourParam3 = input.bool(true, "Enable Feature", group="Your Indicator")
```

### Bước 3: Tính Toán Chỉ Báo / Step 3: Calculate Indicator

Thêm công thức tính toán vào phần **INDICATOR CALCULATIONS**:

```pine
// Your Indicator Calculation
yourIndicator = ta.sma(close, yourParam1)
yourSignal = close > yourIndicator
```

### Bước 4: Cập nhật Điều Kiện Tín Hiệu / Step 4: Update Signal Conditions

Cập nhật phần **SIGNAL CONDITIONS** để sử dụng chỉ báo mới:

```pine
// Updated Entry Signals
longCondition = bullishCrossover and rsi < 70 and macdBullish and yourSignal and inTimeRange
shortCondition = bearishCrossover and rsi > 30 and macdBearish and not yourSignal and inTimeRange
```

### Bước 5: Vẽ Chỉ Báo / Step 5: Plot Indicator

Thêm vào phần **PLOT INDICATORS** nếu muốn hiển thị:

```pine
// Plot your indicator
plot(yourIndicator, "Your Indicator", color=color.new(color.yellow, 0), linewidth=1)
```

---

## 🎯 Ví Dụ Cụ Thể / Specific Examples

### Example 1: Thêm Bollinger Bands

```pine
// === Bollinger Bands Settings ===
bbLength = input.int(20, "BB Length", minval=1, group="Bollinger Bands")
bbStdDev = input.float(2.0, "BB StdDev", minval=0.1, step=0.1, group="Bollinger Bands")

// Calculate Bollinger Bands
[bbMiddle, bbUpper, bbLower] = ta.bb(close, bbLength, bbStdDev)

// Signal Conditions
bbOverbought = close > bbUpper
bbOversold = close < bbLower

// Updated Entry Signals
longCondition = bullishCrossover and rsi < 70 and macdBullish and bbOversold and inTimeRange
shortCondition = bearishCrossover and rsi > 30 and macdBearish and bbOverbought and inTimeRange

// Plot Bollinger Bands
p1 = plot(bbUpper, "BB Upper", color=color.new(color.gray, 50))
p2 = plot(bbLower, "BB Lower", color=color.new(color.gray, 50))
plot(bbMiddle, "BB Middle", color=color.new(color.gray, 70), linewidth=1)
fill(p1, p2, color=color.new(color.gray, 90))
```

### Example 2: Thêm Stochastic Oscillator

```pine
// === Stochastic Settings ===
stochK = input.int(14, "Stoch %K Length", minval=1, group="Stochastic")
stochD = input.int(3, "Stoch %D Smoothing", minval=1, group="Stochastic")
stochSmooth = input.int(3, "Stoch Smoothing", minval=1, group="Stochastic")

// Calculate Stochastic
stochValue = ta.stoch(close, high, low, stochK)
stochSignal = ta.sma(stochValue, stochSmooth)
stochD_line = ta.sma(stochSignal, stochD)

// Conditions
stochOversold = stochValue < 20
stochOverbought = stochValue > 80
stochBullishCross = ta.crossover(stochValue, stochD_line)
stochBearishCross = ta.crossunder(stochValue, stochD_line)

// Updated Entry Signals
longCondition = bullishCrossover and rsi < 70 and macdBullish and stochOversold and inTimeRange
shortCondition = bearishCrossover and rsi > 30 and macdBearish and stochOverbought and inTimeRange
```

### Example 3: Thêm ATR cho Dynamic Stop Loss

```pine
// === ATR Settings ===
atrLength = input.int(14, "ATR Length", minval=1, group="ATR")
atrMultiplier = input.float(2.0, "ATR Multiplier", minval=0.1, step=0.1, group="ATR")

// Calculate ATR
atrValue = ta.atr(atrLength)

// Dynamic Stop Loss based on ATR
longStopLoss = useStopLoss ? close - (atrValue * atrMultiplier) : na
shortStopLoss = useStopLoss ? close + (atrValue * atrMultiplier) : na

// Use in strategy.exit
if longCondition and strategy.position_size == 0
    strategy.entry("Long", strategy.long)
    strategy.exit("Long Exit", "Long", stop=longStopLoss)
```

### Example 4: Thêm Volume Confirmation

```pine
// === Volume Settings ===
volumeMA_length = input.int(20, "Volume MA Length", minval=1, group="Volume")
volumeMultiplier = input.float(1.5, "Volume Multiplier", minval=1.0, step=0.1, group="Volume")

// Calculate Volume
volumeMA = ta.sma(volume, volumeMA_length)
highVolume = volume > volumeMA * volumeMultiplier

// Updated Entry Signals with Volume Confirmation
longCondition = bullishCrossover and rsi < 70 and macdBullish and highVolume and inTimeRange
shortCondition = bearishCrossover and rsi > 30 and macdBearish and highVolume and inTimeRange
```

### Example 5: Thêm Ichimoku Cloud

```pine
// === Ichimoku Settings ===
conversionPeriods = input.int(9, "Conversion Line Length", minval=1, group="Ichimoku")
basePeriods = input.int(26, "Base Line Length", minval=1, group="Ichimoku")
laggingSpan2Periods = input.int(52, "Lagging Span 2 Length", minval=1, group="Ichimoku")
displacement = input.int(26, "Displacement", minval=1, group="Ichimoku")

// Calculate Ichimoku
donchian(len) =>
    math.avg(ta.lowest(len), ta.highest(len))

conversionLine = donchian(conversionPeriods)
baseLine = donchian(basePeriods)
leadLine1 = math.avg(conversionLine, baseLine)
leadLine2 = donchian(laggingSpan2Periods)

// Cloud conditions
aboveCloud = close > math.max(leadLine1[displacement], leadLine2[displacement])
belowCloud = close < math.min(leadLine1[displacement], leadLine2[displacement])

// Updated Entry Signals
longCondition = bullishCrossover and rsi < 70 and macdBullish and aboveCloud and inTimeRange
shortCondition = bearishCrossover and rsi > 30 and macdBearish and belowCloud and inTimeRange

// Plot Ichimoku
plot(conversionLine, "Conversion", color=color.blue)
plot(baseLine, "Base", color=color.red)
p1 = plot(leadLine1[displacement], "Lead 1", color=color.green)
p2 = plot(leadLine2[displacement], "Lead 2", color=color.red)
fill(p1, p2, color=leadLine1[displacement] > leadLine2[displacement] ? color.new(color.green, 90) : color.new(color.red, 90))
```

---

## 🔧 Template Chỉ Báo Tùy Chỉnh / Custom Indicator Template

Sử dụng template này để thêm chỉ báo mới:

```pine
//@version=5
strategy("Your Custom Strategy", overlay=true)

// ============================================
// INPUT PARAMETERS
// ============================================

// [Your indicator parameters here]
param1 = input.int(14, "Parameter 1")
param2 = input.float(2.0, "Parameter 2")

// ============================================
// INDICATOR CALCULATIONS
// ============================================

// [Your indicator calculations here]
myIndicator = [your calculation]

// ============================================
// SIGNAL CONDITIONS
// ============================================

// [Your signal conditions here]
longCondition = [your long condition]
shortCondition = [your short condition]

// ============================================
// RISK MANAGEMENT
// ============================================

stopLossPercent = input.float(2.0, "Stop Loss %")
takeProfitPercent = input.float(4.0, "Take Profit %")

longStopLoss = close * (1 - stopLossPercent/100)
longTakeProfit = close * (1 + takeProfitPercent/100)
shortStopLoss = close * (1 + stopLossPercent/100)
shortTakeProfit = close * (1 - takeProfitPercent/100)

// ============================================
// EXECUTE ORDERS
// ============================================

if longCondition and strategy.position_size == 0
    strategy.entry("Long", strategy.long)
    strategy.exit("Long Exit", "Long", stop=longStopLoss, limit=longTakeProfit)

if shortCondition and strategy.position_size == 0
    strategy.entry("Short", strategy.short)
    strategy.exit("Short Exit", "Short", stop=shortStopLoss, limit=shortTakeProfit)

// ============================================
// PLOT INDICATORS
// ============================================

plot(myIndicator, "My Indicator", color=color.yellow)
plotshape(longCondition, "Long", shape.triangleup, location.belowbar, color=color.green)
plotshape(shortCondition, "Short", shape.triangledown, location.abovebar, color=color.red)
```

---

## 💡 Lời Khuyên / Tips

### 1. Test từng bước / Test Step by Step
- Thêm một chỉ báo tại một thời điểm
- Test trên dữ liệu lịch sử (backtest)
- Xác nhận kết quả trước khi thêm chỉ báo tiếp theo

### 2. Kết hợp nhiều chỉ báo / Combine Multiple Indicators
- Sử dụng toán tử logic: `and`, `or`, `not`
- Ví dụ: `longCondition = ma_signal and rsi_signal and volume_signal`

### 3. Tối ưu hóa thông số / Optimize Parameters
- Sử dụng Strategy Tester của TradingView
- Test với nhiều bộ thông số khác nhau
- Tìm bộ thông số tối ưu cho từng cặp tiền

### 4. Backtesting
- Test trên ít nhất 6-12 tháng dữ liệu
- Kiểm tra trên nhiều điều kiện thị trường khác nhau
- Xem xét Win Rate, Profit Factor, Max Drawdown

### 5. Forward Testing
- Test trên tài khoản demo trước
- Theo dõi hiệu suất trong thời gian thực
- Điều chỉnh nếu cần thiết

---

## 📚 Tài Nguyên Học Tập / Learning Resources

### Pine Script Documentation
- https://www.tradingview.com/pine-script-docs/
- https://www.tradingview.com/pine-script-reference/

### Built-in Indicators in Pine Script
- `ta.sma()` - Simple Moving Average
- `ta.ema()` - Exponential Moving Average
- `ta.rsi()` - Relative Strength Index
- `ta.macd()` - MACD
- `ta.bb()` - Bollinger Bands
- `ta.stoch()` - Stochastic
- `ta.atr()` - Average True Range
- `ta.cci()` - Commodity Channel Index
- `ta.adx()` - Average Directional Index
- `ta.obv()` - On Balance Volume

### Common Functions
- `ta.crossover(a, b)` - A crosses above B
- `ta.crossunder(a, b)` - A crosses below B
- `ta.highest(source, length)` - Highest value
- `ta.lowest(source, length)` - Lowest value
- `ta.change(source)` - Change from previous bar
- `ta.mom(source, length)` - Momentum

---

## ❓ Câu Hỏi Thường Gặp / FAQ

### Q: Làm sao để chỉ giao dịch một chiều (chỉ Long hoặc chỉ Short)?

```pine
allowLong = input.bool(true, "Allow Long Trades")
allowShort = input.bool(true, "Allow Short Trades")

if longCondition and strategy.position_size == 0 and allowLong
    strategy.entry("Long", strategy.long)

if shortCondition and strategy.position_size == 0 and allowShort
    strategy.entry("Short", strategy.short)
```

### Q: Làm sao để giới hạn số lệnh trong ngày?

```pine
var int tradesCount = 0
maxTradesPerDay = input.int(3, "Max Trades Per Day")

if ta.change(time('D'))
    tradesCount := 0

if longCondition and strategy.position_size == 0 and tradesCount < maxTradesPerDay
    strategy.entry("Long", strategy.long)
    tradesCount += 1
```

### Q: Làm sao để tránh giao dịch trong tin tức?

```pine
// Định nghĩa các khung thời gian tránh (theo UTC)
avoidHour1 = input.int(14, "Avoid Hour 1")
avoidHour2 = input.int(18, "Avoid Hour 2")

currentHour = hour(time)
isNewsTime = currentHour == avoidHour1 or currentHour == avoidHour2

if longCondition and strategy.position_size == 0 and not isNewsTime
    strategy.entry("Long", strategy.long)
```

---

**Chúc bạn tùy chỉnh thành công! 🚀**
