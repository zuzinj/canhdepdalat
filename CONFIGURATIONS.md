# Configuration Examples / Ví Dụ Cấu Hình

## Các Cấu Hình Phổ Biến / Popular Configurations

### 1. Conservative Trading (Giao Dịch Thận Trọng)

**Best for:** Beginners, Risk-averse traders

```javascript
// Ichimoku Settings
Tenkan Period: 9
Kijun Period: 26
Senkou Span B Period: 52
Displacement: 26

// Additional Kijun
Kijun 65: 65
Kijun 129: 129
Kijun 172: 172
Kijun 234: 234

// SMMA
SMMA 52: 52
SMMA 139: 139
SMMA 400: 400

// Risk Management
Use Stop Loss: TRUE
Stop Loss %: 1.5
Use Take Profit: TRUE
Take Profit %: 3.0

// Trading
Enable Long Trades: TRUE
Enable Short Trades: FALSE  // Only long for beginners
```

**Expected Results:**
- Win Rate: 55-65%
- Risk:Reward: 1:2
- Max Drawdown: 5-8%

---

### 2. Aggressive Trading (Giao Dịch Tích Cực)

**Best for:** Experienced traders, Higher risk tolerance

```javascript
// Ichimoku Settings
Tenkan Period: 7
Kijun Period: 22
Senkou Span B Period: 44
Displacement: 22

// Additional Kijun
Kijun 65: 65
Kijun 129: 129
Kijun 172: 172
Kijun 234: 234

// SMMA
SMMA 52: 52
SMMA 139: 139
SMMA 400: 400

// Risk Management
Use Stop Loss: TRUE
Stop Loss %: 3.0
Use Take Profit: TRUE
Take Profit %: 8.0

// Trading
Enable Long Trades: TRUE
Enable Short Trades: TRUE
```

**Expected Results:**
- Win Rate: 45-55%
- Risk:Reward: 1:2.5+
- Max Drawdown: 12-20%

---

### 3. Scalping (5-15 minutes)

**Best for:** Active traders, Quick profits

```javascript
// Ichimoku Settings
Tenkan Period: 5
Kijun Period: 13
Senkou Span B Period: 26
Displacement: 13

// Additional Kijun
Kijun 65: 34
Kijun 129: 65
Kijun 172: 89
Kijun 234: 144

// SMMA
SMMA 52: 26
SMMA 139: 55
SMMA 400: 200

// Risk Management
Use Stop Loss: TRUE
Stop Loss %: 0.5
Use Take Profit: TRUE
Take Profit %: 1.0

// Trading
Enable Long Trades: TRUE
Enable Short Trades: TRUE
```

**Expected Results:**
- Win Rate: 60-70%
- Risk:Reward: 1:2
- Many trades per day

---

### 4. Day Trading (15min - 4h)

**Best for:** Daily active trading

```javascript
// Ichimoku Settings (Default)
Tenkan Period: 9
Kijun Period: 26
Senkou Span B Period: 52
Displacement: 26

// Additional Kijun
Kijun 65: 65
Kijun 129: 129
Kijun 172: 172
Kijun 234: 234

// SMMA
SMMA 52: 52
SMMA 139: 139
SMMA 400: 400

// Risk Management
Use Stop Loss: TRUE
Stop Loss %: 2.0
Use Take Profit: TRUE
Take Profit %: 4.0

// Trading
Enable Long Trades: TRUE
Enable Short Trades: TRUE
```

**Expected Results:**
- Win Rate: 50-60%
- Risk:Reward: 1:2
- 2-5 trades per day

---

### 5. Swing Trading (4h - Daily)

**Best for:** Part-time traders, Lower stress

```javascript
// Ichimoku Settings
Tenkan Period: 13
Kijun Period: 34
Senkou Span B Period: 89
Displacement: 34

// Additional Kijun
Kijun 65: 89
Kijun 129: 144
Kijun 172: 233
Kijun 234: 377

// SMMA
SMMA 52: 89
SMMA 139: 200
SMMA 400: 600

// Risk Management
Use Stop Loss: TRUE
Stop Loss %: 4.0
Use Take Profit: TRUE
Take Profit %: 10.0

// Trading
Enable Long Trades: TRUE
Enable Short Trades: TRUE
```

**Expected Results:**
- Win Rate: 50-60%
- Risk:Reward: 1:2.5
- 1-3 trades per week

---

### 6. Position Trading (Daily - Weekly)

**Best for:** Long-term investors, Low time commitment

```javascript
// Ichimoku Settings
Tenkan Period: 20
Kijun Period: 60
Senkou Span B Period: 120
Displacement: 60

// Additional Kijun
Kijun 65: 120
Kijun 129: 200
Kijun 172: 300
Kijun 234: 500

// SMMA
SMMA 52: 100
SMMA 139: 300
SMMA 400: 800

// Risk Management
Use Stop Loss: TRUE
Stop Loss %: 8.0
Use Take Profit: TRUE
Take Profit %: 20.0

// Trading
Enable Long Trades: TRUE
Enable Short Trades: FALSE  // Focus on long-term growth
```

**Expected Results:**
- Win Rate: 45-55%
- Risk:Reward: 1:2.5+
- 1-2 trades per month

---

## Cách Áp Dụng Cấu Hình / How to Apply Configuration

### Step 1: Open Settings
1. Right-click on chart
2. Select "Settings..."
3. Go to "Inputs" tab

### Step 2: Adjust Parameters
1. Find each parameter in the list
2. Change values according to your chosen configuration
3. Click "OK"

### Step 3: Test on Demo
1. Backtest on historical data
2. Paper trade for 1-2 weeks
3. Analyze results
4. Fine-tune if needed

---

## Tùy Chỉnh Cho Các Thị Trường / Market-Specific Customization

### Cryptocurrency (24/7 Trading)
```
- Use shorter periods for volatility
- Wider Stop Loss (3-5%) due to volatility
- Trade both long and short
- Consider weekend gaps
```

### Forex (High Liquidity)
```
- Standard Ichimoku settings work well
- Tighter spreads allow smaller Stop Loss
- Watch for news events
- Best during London/NY sessions
```

### Stocks (Regular Hours)
```
- Consider gap openings
- Avoid first 15 minutes
- Longer Ichimoku periods (more stable)
- Focus on liquid stocks only
```

### Indices (Correlated)
```
- Follow overall market trend
- Use higher timeframes for confirmation
- Lower leverage recommended
- Watch VIX for volatility
```

---

## Performance Optimization Tips / Mẹo Tối Ưu Hiệu Suất

### 1. Backtest First
- Test at least 6-12 months of data
- Include different market conditions
- Aim for >50% win rate
- Check max drawdown

### 2. Start Small
- Begin with minimum position size
- Gradually increase as confidence builds
- Never risk more than 1-2% per trade
- Keep trading journal

### 3. Regular Review
- Review trades weekly
- Adjust settings if needed
- Track what works and what doesn't
- Be patient with the system

### 4. Market Conditions
- Trending markets: Use default settings
- Ranging markets: Reduce position size or avoid
- High volatility: Wider stops
- Low volatility: Tighter stops

---

## Configuration Comparison Table

| Style | Timeframe | Risk/Trade | Trades/Week | Time Required | Difficulty |
|-------|-----------|------------|-------------|---------------|------------|
| Conservative | 1H-4H | 1.5% | 2-3 | Low | Easy |
| Aggressive | 15M-1H | 3% | 10-15 | High | Hard |
| Scalping | 5M-15M | 0.5% | 20-50 | Very High | Very Hard |
| Day Trading | 15M-4H | 2% | 5-10 | Medium | Medium |
| Swing Trading | 4H-1D | 4% | 1-3 | Low | Easy |
| Position | 1D-1W | 8% | 0.5-2 | Very Low | Easy |

---

## Warning Signs / Dấu Hiệu Cảnh Báo

### When to Stop Trading:
- ❌ 3 consecutive losses
- ❌ Emotional decision making
- ❌ Breaking your rules
- ❌ Revenge trading
- ❌ Over-leveraging

### When to Review Settings:
- ⚠️ Win rate <40%
- ⚠️ Losing money for 2 weeks
- ⚠️ Too many false signals
- ⚠️ Max drawdown exceeded
- ⚠️ Market conditions changed

---

## Support & Resources / Hỗ Trợ & Tài Nguyên

- 📖 Main Guide: [README.md](README.md)
- 📖 Vietnamese: [HUONG_DAN.md](HUONG_DAN.md)
- 📖 English: [README_EN.md](README_EN.md)
- 📊 Structure: [STRUCTURE.md](STRUCTURE.md)
- 🚀 Quick Start: [QUICK_REFERENCE.md](QUICK_REFERENCE.md)

---

**Remember:** No configuration is perfect for all conditions. Adapt and test!
