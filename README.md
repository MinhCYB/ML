# ASM 8 ML

## 1. K-Means Clustering
Thuật toán phân chia dữ liệu thành $k$ cụm cố định dựa trên khoảng cách.

**Các bước thực hiện:**
1. **Khởi tạo:** Chọn ngẫu nhiên $k$ điểm làm tâm cụm ban đầu (centroids).
2. **Gán cụm:** Tính khoảng cách từ mỗi điểm dữ liệu đến $k$ tâm cụm. Điểm nào gần tâm nào nhất thì thuộc về cụm đó.
3. **Cập nhật tâm:** Tính toán lại vị trí tâm cụm bằng cách lấy trung bình cộng tọa độ của tất cả các điểm trong cụm đó.
4. **Lặp lại:** Thực hiện lại bước 2 và 3 cho đến khi vị trí các tâm cụm không còn thay đổi đáng kể (hội tụ).

## 2. Hierarchical Clustering 
Xây dựng cấu trúc phân cấp các cụm theo dạng cây (Dendrogram). Ở đây tập trung vào phương pháp **Agglomerative** (từ dưới lên).

**Các bước thực hiện:**
1. **Khởi tạo:** Coi mỗi điểm dữ liệu là một cụm riêng biệt.
2. **Tìm cặp gần nhất:** Tính toán khoảng cách giữa tất cả các cụm và tìm cặp 2 cụm có khoảng cách ngắn nhất.
3. **Gộp cụm:** Gộp 2 cụm gần nhất đó thành một cụm lớn hơn.
4. **Cập nhật:** Tính lại khoảng cách giữa cụm mới gộp và các cụm còn lại.
5. **Lặp lại:** Tiếp tục gộp cho đến khi tất cả các điểm nằm chung trong một cụm duy nhất.
6. **Cắt cây:** Dựa vào biểu đồ Dendrogram để chọn số lượng cụm phù hợp bằng cách cắt ngang cây ở độ cao mong muốn.

## 3. Expectation-Maximization (EM) Algorithm
Thuật toán tối ưu hóa lặp để ước lượng tham số trong các mô hình xác suất (phổ biến nhất là Gaussian Mixture Model - GMM).

**Các bước thực hiện:**
1. **Khởi tạo:** Chọn các thông số ban đầu cho các cụm (Trung bình $\mu$, Phương sai $\sigma$, và Trọng số $\pi$).
2. **Bước E (Expectation - Kỳ vọng):** Dựa trên các tham số hiện tại, tính xác suất (trách nhiệm) để mỗi điểm dữ liệu thuộc về từng cụm khác nhau.
3. **Bước M (Maximization - Tối đa hóa):** Cập nhật lại các tham số ($\mu, \sigma, \pi$) bằng cách sử dụng xác suất đã tính ở bước E để tối đa hóa hàm hợp lý (Likelihood) của dữ liệu.
4. **Lặp lại:** Thực hiện liên tục bước E và M cho đến khi các tham số ổn định hoặc hàm Likelihood đạt mức tối ưu.