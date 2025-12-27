# Hướng Dẫn Sử Dụng EA TradingView - Ichimoku Multi-Kijun

## Giới Thiệu

EA (Expert Advisor) này được xây dựng dựa trên hệ thống Ichimoku với các đường Kijun bổ sung và SMMA để tạo ra một hệ thống giao dịch đa chu kỳ.

## Các Thành Phần Chính

### 1. Ichimoku Cơ Bản (9, 26, 52, 26)

- **Tenkan-sen (Conversion Line)**: Đường chuyển đổi 9 chu kỳ (màu đỏ)
- **Kijun-sen (Base Line)**: Đường cơ sở 26 chu kỳ (màu xanh dương)
- **Senkou Span A & B**: Tạo thành đám mây Kumo (màu xanh lá/đỏ)
- **Chikou Span**: Đường trễ 26 chu kỳ (màu tím)

### 2. Các Đường Kijun Bổ Sung

- **Kijun 65**: Màu đen - Chu kỳ 65
- **Kijun 129**: Màu xanh dương - Chu kỳ 129
- **Kijun 172**: Màu xanh lá - Chu kỳ 172
- **Kijun 234**: Màu cam - Chu kỳ 234

### 3. Các Đường SMMA (Smoothed Moving Average)

- **SMMA 52**: Màu hồng - Chu kỳ 52
- **SMMA 139**: Màu xanh cyan - Chu kỳ 139
- **SMMA 400**: Màu vàng - Chu kỳ 400

## Cách Cài Đặt

### Bước 1: Mở TradingView
1. Truy cập https://www.tradingview.com
2. Đăng nhập vào tài khoản của bạn

### Bước 2: Mở Pine Editor
1. Nhấn vào "Pine Editor" ở dưới cùng màn hình
2. Nhấn "New" để tạo script mới

### Bước 3: Copy Code
1. Mở file `tradingview_ea.pine`
2. Copy toàn bộ nội dung
3. Paste vào Pine Editor

### Bước 4: Lưu và Thêm vào Chart
1. Nhấn "Save" và đặt tên cho script
2. Nhấn "Add to Chart" để áp dụng lên biểu đồ

## Tín Hiệu Giao Dịch

### Tín Hiệu Mua (Long)
- ✅ Tenkan-sen cắt lên trên Kijun-sen
- ✅ Giá nằm trên đám mây Kumo
- 🔺 Biểu tượng mũi tên xanh xuất hiện dưới nến

### Tín Hiệu Bán (Short)
- ❌ Tenkan-sen cắt xuống dưới Kijun-sen
- ❌ Giá nằm dưới đám mây Kumo
- 🔻 Biểu tượng mũi tên đỏ xuất hiện trên nến

## Quản Lý Rủi Ro

### Stop Loss
- Mặc định: 2% từ giá vào lệnh
- Có thể điều chỉnh trong Settings

### Take Profit
- Mặc định: 4% từ giá vào lệnh
- Có thể điều chỉnh trong Settings

## Cách Sử Dụng

### 1. Phân Tích Xu Hướng
- Quan sát vị trí giá so với đám mây Kumo
- Màu xanh lá: Xu hướng tăng mạnh
- Màu đỏ: Xu hướng giảm mạnh

### 2. Xác Nhận Tín Hiệu
- Kiểm tra các đường Kijun bổ sung để xác nhận xu hướng
- Các đường SMMA giúp xác định xu hướng dài hạn

### 3. Vào Lệnh
- Chờ tín hiệu từ system (mũi tên xanh/đỏ)
- Kiểm tra volume và các yếu tố khác
- Vào lệnh khi tất cả điều kiện thỏa mãn

## Tùy Chỉnh

### Trong Settings của Strategy:

#### Ichimoku Basic
- Điều chỉnh các chu kỳ Tenkan, Kijun, Senkou Span B
- Thay đổi displacement (dịch chuyển)

#### Additional Kijun
- Tùy chỉnh các chu kỳ Kijun bổ sung (65, 129, 172, 234)

#### SMMA
- Điều chỉnh các chu kỳ SMMA (52, 139, 400)

#### Risk Management
- Bật/tắt Stop Loss và Take Profit
- Điều chỉnh % Stop Loss và Take Profit

#### Trading
- Bật/tắt giao dịch Long hoặc Short

## Lưu Ý Quan Trọng

⚠️ **Cảnh báo**: 
- EA này chỉ mang tính chất tham khảo
- Luôn kiểm tra kỹ trên tài khoản demo trước
- Không nên sử dụng toàn bộ vốn cho một lệnh
- Giao dịch có rủi ro, chỉ dùng vốn có thể chấp nhận mất

## Backtesting

1. Mở Strategy Tester trong TradingView
2. Chọn khung thời gian và khoảng thời gian muốn test
3. Xem kết quả:
   - Net Profit
   - Win Rate
   - Max Drawdown
   - Profit Factor

## Hỗ Trợ

Nếu có thắc mắc hoặc cần hỗ trợ, vui lòng tạo issue trên GitHub repository.

## Phiên Bản

- **Version**: 1.0
- **Pine Script**: Version 5
- **Ngày tạo**: 2025-12-27

## Tác Giả

Repository: https://github.com/zuzinj/canhdepdalat
