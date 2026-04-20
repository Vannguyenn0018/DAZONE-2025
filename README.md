# 🚀 DAZONE 2025 🚀
### *Case Study: Dự đoán hành vi mua sắm trên nền tảng Thương mại điện tử Viettel*

---

## 📌 Tổng quan dự án
Dự án này được thực hiện trong khuôn khổ cuộc thi **DAZONE 2025** (do Viettel tổ chức). Mục tiêu cốt lõi là phân tích tập dữ liệu TMĐT khổng lồ (hơn 50 triệu bản ghi) để tìm ra quy luật của nhóm **Deal Hunters** và dự đoán những khách hàng tiềm năng sẽ trở thành **khách hàng trung thành** bằng cách quay lại mua hàng trong vòng 6 tháng.
## 🎯 Mục tiêu chính: Trả lời cho các câu hỏi về bài toán doanh nghiệp

* Làm sao để xác định người dùng nào có khả năng quay lại mua hàng trong
tương lai?
* Khách hàng nào có tiềm năng trở thành khách hàng trung thành?
* Dự đoán xác suất để mỗi người dùng mới quay lại mua hàng từ cùng một gian
hàng trong vòng 6 tháng tới

## 📊 Các Insight quan trọng (Kết quả EDA)
Qua quá trình **Khám phá dữ liệu (EDA)**, nhóm đã tìm ra những thông tin đắt giá cho doanh nghiệp:
* **Đỉnh cao mua sắm 11/11:** Lượng truy cập tăng vọt vào ngày 11/11, xác nhận sự tồn tại của tệp khách hàng chỉ chờ khuyến mãi lớn.
* **Chân dung khách hàng:** **66.5%** khách hàng là Nữ, độ tuổi tập trung chủ yếu từ **20 đến 40 tuổi**.
* **Chỉ số trung thành:** Nhóm đã xác định được **229,940 người dùng** có hành vi mua lặp lại (`total_repeat_shops > 0`). Đây là nhóm khách hàng "hạt nhân" cần tập trung Remarketing.
* **Mất cân bằng dữ liệu:** Tỉ lệ khách quay lại chỉ chiếm khoảng 10%, do đó nhóm đề xuất dùng **F1-Score** và **AUC-ROC** để đánh giá mô hình thay vì Accuracy.

## 🛠️ Xử lý dữ liệu & Kỹ thuật đặc trưng (Feature Engineering)
- **Làm sạch:** Xử lý các giá trị ngoại lệ (Tuổi -1/999) và chuẩn hóa giới tính (chuyển các nhãn không đồng nhất về "Nữ", "Nam", "Chưa xác định").
- **Lọc trùng:** Đảm bảo tính toàn vẹn của dữ liệu bằng cách loại bỏ các dòng trùng lặp trong bộ 41 triệu logs.
- **Xây dựng đặc trưng mới:**
    - `user_conversion_rate`: Tỷ lệ từ lượt click sang lượt mua của mỗi user.
    - `total_repeat_shops`: Số lượng gian hàng mà user đã quay lại mua lần thứ 2 trở lên.
    - `last_active_day`: Chỉ số về thời điểm hoạt động gần nhất (Recency).

## 💻 Công nghệ sử dụng
- **Ngôn ngữ:** Python
- **Môi trường:** Kaggle Notebook
- **Thư viện:** Pandas, NumPy, Matplotlib, Seaborn

## 📂 Cấu trúc dự án
```text
├── DAZONE_25.ipynb # Toàn bộ code xử lý, EDA và tạo Feature
├── REPORT_DAZONE_25.pdf   # Bản báo cáo chi tiết gửi Ban giám khảo
└── README.md                     # Hướng dẫn và giới thiệu dự án
```
### 🧑‍💻 Nguyễn Thái Thanh Vân
Email: vanthanhh8100@gmail.com
