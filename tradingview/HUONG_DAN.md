# Hướng Dẫn Sử Dụng TradingView EA - Cảnh Đẹp Đà Lạt

## 📊 Giới Thiệu

Bộ công cụ này bao gồm:
1. **indicator.pine** - Chỉ báo (Indicator) để phân tích thị trường
2. **strategy_ea.pine** - Expert Advisor (EA/Strategy) để giao dịch tự động

## 🚀 Cách Cài Đặt

### 1. Cài đặt Indicator (Chỉ báo)

1. Mở TradingView (https://www.tradingview.com/)
2. Nhấn vào **Pine Editor** ở phía dưới màn hình
3. Copy toàn bộ nội dung file `indicator.pine`
4. Paste vào Pine Editor
5. Nhấn **"Save"** và đặt tên cho chỉ báo
6. Nhấn **"Add to Chart"** để thêm vào biểu đồ

### 2. Cài đặt Strategy EA (Chiến lược giao dịch tự động)

1. Mở TradingView
2. Nhấn vào **Pine Editor**
3. Copy toàn bộ nội dung file `strategy_ea.pine`
4. Paste vào Pine Editor
5. Nhấn **"Save"** và đặt tên cho strategy
6. Nhấn **"Add to Chart"** để thêm vào biểu đồ

## ⚙️ Thông Số Cấu Hình

### Moving Average (Đường Trung Bình)
- **Fast MA Length**: Độ dài MA nhanh (mặc định: 9)
- **Slow MA Length**: Độ dài MA chậm (mặc định: 21)
- **MA Type**: Loại MA (SMA hoặc EMA)

### RSI (Relative Strength Index)
- **RSI Length**: Độ dài RSI (mặc định: 14)
- **RSI Overbought**: Ngưỡng quá mua (mặc định: 70)
- **RSI Oversold**: Ngưỡng quá bán (mặc định: 30)

### MACD (Moving Average Convergence Divergence)
- **MACD Fast Length**: Độ dài MACD nhanh (mặc định: 12)
- **MACD Slow Length**: Độ dài MACD chậm (mặc định: 26)
- **MACD Signal Length**: Độ dài tín hiệu MACD (mặc định: 9)

### Risk Management (Quản lý rủi ro) - Chỉ có trong Strategy EA

#### Stop Loss và Take Profit
- **Use Stop Loss**: Bật/tắt stop loss
- **Stop Loss %**: Phần trăm stop loss (mặc định: 2%)
- **Use Take Profit**: Bật/tắt take profit
- **Take Profit %**: Phần trăm take profit (mặc định: 4%)
- **Use Trailing Stop**: Bật/tắt trailing stop
- **Trailing Stop %**: Phần trăm trailing stop (mặc định: 1.5%)

#### Position Sizing (Kích thước vị thế)
- **Risk Per Trade**: Phần trăm vốn mạo hiểm mỗi lệnh (mặc định: 100%)

#### Trading Hours (Giờ giao dịch)
- **Use Time Filter**: Bật/tắt bộ lọc thời gian
- **Start Hour**: Giờ bắt đầu giao dịch
- **End Hour**: Giờ kết thúc giao dịch

## 📈 Logic Giao Dịch

### Tín Hiệu MUA (LONG)
Điều kiện để vào lệnh MUA:
1. ✅ Fast MA cắt lên trên Slow MA (bullish crossover)
2. ✅ RSI < 70 (không ở vùng quá mua)
3. ✅ MACD Line > Signal Line và Histogram > 0 (xu hướng tăng)

### Tín Hiệu BÁN (SHORT)
Điều kiện để vào lệnh BÁN:
1. ✅ Fast MA cắt xuống dưới Slow MA (bearish crossover)
2. ✅ RSI > 30 (không ở vùng quá bán)
3. ✅ MACD Line < Signal Line và Histogram < 0 (xu hướng giảm)

### Điều Kiện Thoát Lệnh

**Thoát lệnh LONG:**
- Fast MA cắt xuống Slow MA, hoặc
- RSI > 70 (quá mua), hoặc
- MACD Line cắt xuống Signal Line

**Thoát lệnh SHORT:**
- Fast MA cắt lên Slow MA, hoặc
- RSI < 30 (quá bán), hoặc
- MACD Line cắt lên Signal Line

## 🔔 Thiết Lập Cảnh Báo (Alerts)

### Trong Indicator:
1. Nhấn chuột phải vào chỉ báo trên biểu đồ
2. Chọn **"Add Alert"**
3. Chọn điều kiện:
   - Buy Alert: Cảnh báo tín hiệu mua
   - Sell Alert: Cảnh báo tín hiệu bán

### Trong Strategy EA:
1. Nhấn vào biểu tượng Alert (⏰) trên thanh công cụ
2. Chọn điều kiện:
   - Long Entry Alert: Cảnh báo vào lệnh mua
   - Short Entry Alert: Cảnh báo vào lệnh bán
   - Long Exit Alert: Cảnh báo thoát lệnh mua
   - Short Exit Alert: Cảnh báo thoát lệnh bán

## 📊 Hiển Thị Trên Biểu Đồ

### Indicator hiển thị:
- 📈 Đường màu xanh dương: Fast MA
- 📈 Đường màu đỏ: Slow MA
- ▲ Mũi tên xanh hướng lên: Tín hiệu mua
- ▼ Mũi tên đỏ hướng xuống: Tín hiệu bán
- 🟢 Nền xanh nhạt: Xu hướng tăng
- 🔴 Nền đỏ nhạt: Xu hướng giảm

### Strategy EA hiển thị thêm:
- Tất cả các yếu tố của Indicator
- 📊 Bảng thông tin vị thế (góc phải trên):
  - Trạng thái vị thế (LONG/SHORT/NONE)
  - Giá vào lệnh
  - Kích thước vị thế
  - Lãi/lỗ chưa thực hiện
  - Tổng lãi/lỗ
- 🔴 Đường Stop Loss màu đỏ
- 🟢 Đường Take Profit màu xanh

## 💡 Lưu Ý Quan Trọng

1. **Backtest trước khi sử dụng thật**: Luôn kiểm tra chiến lược trên dữ liệu lịch sử
2. **Điều chỉnh thông số**: Mỗi cặp tiền/thị trường khác nhau cần thông số khác nhau
3. **Quản lý rủi ro**: Không nên mạo hiểm quá 1-2% vốn cho mỗi lệnh
4. **Theo dõi thường xuyên**: EA không thay thế hoàn toàn việc giám sát của bạn
5. **Điều kiện thị trường**: Chiến lược hoạt động tốt trong thị trường có xu hướng

## 🔧 Tùy Chỉnh

### Để tùy chỉnh theo chỉ báo riêng của bạn:

1. Mở file `strategy_ea.pine` trong Pine Editor
2. Tìm phần **"TÍNH TOÁN CHỈ BÁO"**
3. Thay thế hoặc thêm công thức tính toán chỉ báo của bạn
4. Cập nhật phần **"ĐIỀU KIỆN TÍN HIỆU"** với logic mới
5. Test và điều chỉnh các thông số

### Ví dụ thêm chỉ báo mới:

```pine
// Thêm Bollinger Bands
bbLength = input.int(20, "BB Length")
bbMult = input.float(2.0, "BB Multiplier")
[bbMiddle, bbUpper, bbLower] = ta.bb(close, bbLength, bbMult)

// Cập nhật điều kiện vào lệnh
longCondition = bullishCrossover and rsi < 70 and macdBullish and close < bbLower
shortCondition = bearishCrossover and rsi > 30 and macdBearish and close > bbUpper
```

## 📞 Hỗ Trợ

- Nếu có lỗi cú pháp, kiểm tra phiên bản Pine Script (phải là v5)
- Đọc tài liệu TradingView: https://www.tradingview.com/pine-script-docs/
- Kiểm tra console để xem thông báo lỗi

## ⚠️ Disclaimer

- Đây là công cụ hỗ trợ giao dịch, không phải lời khuyên đầu tư
- Luôn tự nghiên cứu và chịu trách nhiệm với các quyết định giao dịch của mình
- Giao dịch có rủi ro, có thể mất toàn bộ vốn đầu tư

## 📝 Lịch Sử Phiên Bản

### Version 1.0 (2025-12-25)
- ✅ Tạo chỉ báo cơ bản với MA, RSI, MACD
- ✅ Chuyển đổi sang Strategy EA
- ✅ Thêm quản lý rủi ro (Stop Loss, Take Profit, Trailing Stop)
- ✅ Thêm bộ lọc thời gian giao dịch
- ✅ Hiển thị thông tin vị thế trên biểu đồ
- ✅ Thiết lập cảnh báo cho tất cả tín hiệu

---

**Chúc bạn giao dịch thành công! 🚀📈**
