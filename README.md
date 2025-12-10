# Vietnam Stock Market Analysis & Algorithmic Trading System 📈

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Status](https://img.shields.io/badge/Status-Backtesting_Complete-success)
![Data](https://img.shields.io/badge/Data-FiinQuantX-orange)

## 📖 Giới thiệu (Overview)

Dự án này xây dựng một hệ thống giao dịch thuật toán (Algorithmic Trading System) toàn diện cho thị trường chứng khoán Việt Nam (HOSE, HNX, UPCOM). [cite_start]Hệ thống kết hợp phân tích cơ bản, phân tích kỹ thuật và các mô hình Học máy (Machine Learning/Deep Learning) để tối ưu hóa điểm mua/bán và quản trị rủi ro[cite: 14, 15].

[cite_start]Mục tiêu chính là xây dựng một pipeline tự động từ khâu thu thập dữ liệu, làm sạch, trích xuất đặc trưng (Feature Engineering) đến backtest chiến lược trong điều kiện thị trường biến động[cite: 27, 28].

## 📊 Kết quả Nổi bật (Key Results)

[cite_start]Dựa trên dữ liệu backtest năm 2025, chiến lược đã đạt được hiệu suất vượt trội so với thị trường chung, chứng minh khả năng bảo toàn vốn xuất sắc[cite: 816, 824].

| Metric | Value |
| :--- | :--- |
| **Tổng lợi nhuận (Total Return)** | **+29.35%** |
| **Tỷ lệ chiến thắng (Win Rate)** | **76.92%** |
| **Mức sụt giảm tối đa (Max Drawdown)** | **-4.06%** |
| **Tổng số giao dịch** | 52 |

> [cite_start]*Dữ liệu backtest: 04/01/2022 - 12/09/2025 (Tập trung logic vào 2025)*[cite: 14, 51].

## 🛠️ Phương pháp Tiếp cận (Methodology)

[cite_start]Chiến lược sử dụng mô hình lọc 4 lớp (4-Layer Filtering Strategy) để loại bỏ nhiễu và chọn lọc cổ phiếu tiềm năng nhất[cite: 613].

### 1. Lọc Tài chính (Fundamental Filter)
[cite_start]Loại bỏ các cổ phiếu có sức khỏe tài chính kém dựa trên các chỉ số cơ bản[cite: 617]:
* **Tiêu chí:** $EBIT Margin$, $ROA$, $ROE$, $ROIC$.
* [cite_start]**Ngưỡng lọc:** Sử dụng phương pháp phân vị (quantile) tùy chỉnh theo từng sàn (HOSE, HNX, UPCOM) để đảm bảo tính phù hợp với đặc thù thanh khoản và quy mô[cite: 624, 626].

### 2. Lọc Kỹ thuật (Technical Filter)
[cite_start]Sử dụng Feature Engineering để xác định xu hướng và động lượng[cite: 635]:
* [cite_start]**RSI:** Điều chỉnh ngưỡng quá mua/quá bán linh hoạt (ví dụ: HNX dùng 25-75, UPCOM dùng 20-80)[cite: 640, 641].
* [cite_start]**MACD:** Loại bỏ nhiễu bằng phương pháp độ lệch chuẩn (std) và phân vị[cite: 644].
* [cite_start]**Bollinger Bands:** Sử dụng Bandwidth để đánh giá độ biến động[cite: 651].

### 3. Phân loại Rủi ro (Risk Classifier - Machine Learning)
[cite_start]Sử dụng mô hình **LightGBM Classifier** để dự báo rủi ro sụt giảm (drawdown) trong tương lai[cite: 657].
* [cite_start]**Mục tiêu:** Loại bỏ các mã có khả năng drawdown cao (tệ hơn phân vị 25% của thị trường)[cite: 658].
* [cite_start]**Performance:** Độ chính xác (Accuracy) trên cả 3 sàn đều đạt > 70%[cite: 695].

### 4. Phân loại Tín hiệu (Signal Classifier - Deep Learning)
[cite_start]Sử dụng mô hình **LSTM (Long Short-Term Memory)** để nắm bắt các phụ thuộc chuỗi thời gian (temporal dependencies)[cite: 704].
* [cite_start]**Input:** Chuỗi 10 phiên của các chỉ báo kỹ thuật và giá[cite: 711].
* [cite_start]**Output:** Phân loại tín hiệu Mua/Bán/Giữ[cite: 705].

## 📉 Khám phá Dữ liệu (EDA Highlights)

[cite_start]Dự án thực hiện EDA sâu rộng trên 3 sàn để hiểu rõ hành vi thị trường[cite: 87, 88]:
* [cite_start]**HOSE:** Biến động thấp nhất, phù hợp đầu tư ổn định[cite: 103].
* [cite_start]**UPCOM:** Biến động và rủi ro cao nhất, mang tính mùa vụ mạnh[cite: 104, 119].
* [cite_start]**HNX:** Trung hòa giữa rủi ro và cơ hội[cite: 111].

## ⚙️ Cài đặt & Sử dụng (Installation)

1. **Clone repository:**
   ```bash
   git clone [https://github.com/username/repo-name.git](https://github.com/username/repo-name.git)
   cd repo-name
