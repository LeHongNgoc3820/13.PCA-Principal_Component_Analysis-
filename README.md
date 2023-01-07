# Principal Component Analysis (PCA)
### Nội dung
1. Giới thiệu PCA
2. Các ứng dụng
3. Ưu/khuyết điểm
4. Xây dựng PCA

## 1. Giới thiệu PCA
+ **PCA (Principal Component Analysis)** - phân tích thành phần chính, là một thuật toán dimensionally reduction phổ biến nhất hiện nay.
+ PCA thuộc nhóm **Unsupervised Learning**
+ Kích thước tuyệt đối của dữ liệu hiện nay không chỉ là một thách thức đối với phần cứng máy tính mà còn là nút cổ chai cho hiệu suất của nhiều thuật toán Machine Learning.
+ Mục tiêu chính của phân tích PCA là xác định các mẫu trong dữ liệu. PCA giúp phát hiện mối tương quan giữa các biến. Nếu có mối tương quan chặt chẽ giữa các biến tồn tại, nỗ lực giảm kích thước mới có ý nghĩa.
+ PCA thực hiện việc tìm các hướng của phương sai tối đa (maximum variance) trong dữ liệu high-dimensional và chuyển vào một không gian con có chiều nhỏ hơn và giữ lại hầu hết các thông tin.
+ PCA là một công cụ giảm kích thước có thể được sử dụng để giảm một tập hợp lớn các biến thành một tập nhỏ mà vẫn chứa hầu hết thông tin trong tập hợp lớn.
    + Là một thủ tục toán học biến đổi một số (có thể) các biến tương quan thành một số (nhỏ hơn) các biến không tương quan được gọi là các thành phần chính.
    + Thành phần chính đầu tiên chiếm phần lớn dữ liệu có thể thay đổi và mỗi thành phần kế tiếp chiếm phần lớn các biến còn lại càng tốt.
+ PCA được thực hiện trên một ma trận đối xứng vuông (square symmetric matrix)
    + Nó có thể là Covariance matrix (ma trận hiệp phương sai: thang tỷ lệ hình vuông và đường chéo) hoặc Correlation matrix (ma trận tương quan: tổng số ô vuông và đường chéo từ dữ liệu được chuẩn hoá).
    + Correlation matrix được sử dụng nếu phương sai của các biến riêng lẻ khác nhau nhiều hoặc nếu các đơn vị đo biến thiên riêng rẽ khác nhau.
    
**Mục tiêu:**
+ PCA làm giảm không gian thuộc tính từ một số lượng lớn các biến đến một số lượng nhỏ hơn các yếu tố, là một "non-dependent" procedure, thủ tục "không phụ thuộc" (nó không giả định một biến phụ thuộc cụ thể).
+ PCA là phương pháp nén giảm kích thước hoặc phương pháp nén dữ liệu. Mục tiêu là giảm kích thước nhưng không đảm bảo rằng các chiều có thể diễn giải được.
+ Để chọn một tập con của các biến từ một tập lớn hơn, dựa trên các biến ban đầu có mối tương quan cao nhất với thành phần chính.

## 2. Các ứng dụng
+ Trực quan hoá dữ liệu
+ Nếu thuật toán Machine Learning quá chậm vì kích thước đầu vào quá cao, thì việc sử dụng PCA để tăng tốc là một lựa chọn hợp lý.
+ Nếu bộ nhớ hoặc dung lượng ổ đĩa bị giới hạn, PCA cho phép tiết kiệm không gian để đổi lấy một chút thông tin của dữ liệu. Đây có thể là một sự cân bằng hợp lý.

## 3. Ưu/khuyết điểm
### Ưu điểm
+ Giảm kích thước, tăng tốc độ
+ Trực quan hoá dữ liệu

### Khuyết điểm
+ PCA không thể chỉnh hằng số (scale invariant)
+ Các hướng có phương sai lớn nhất được giả định là quan trọng nhất
+ Chỉ xem xét các phép biến đổi trực giao (các phép quay) của các biến gốc
+ PCA chỉ dựa trên vector trung bình và ma trận hiệp phương sai. Một số phân phối (multivariate normal) đặc trưng bởi điều này, nhưng một số khác thì không.
+ Nếu có các biến tương quan, PCA có thể giảm kích thước. Nếu không, PCA không giảm được kích thước.

## 4. Xây dựng PCA
Dùng `sklearn.decomposition.PCA` để thực hiện:  
+ Việc trực quan hoá dữ liệu
+ Việc tăng tốc độ cho thuật toán Machine Learning

### Việc trực quan hoá dữ liệu
**Các bước thực hiện:**
+ Chọn model sẽ sử dụng là: PCA
+ Chuẩn bị dữ liệu, chuẩn hoá dữ liệu
+ Áp dụng mô hình
+ Trực quan hoá kết quả
+ Giải thích phương sai

### Việc tăng tốc độ cho thuật toán Machine Learning
**Các bước thực hiện:**
+ Chọn model sẽ sử dụng là: PCA
+ Chuẩn bị dữ liệu, chuẩn hoá dữ liệu
+ Áp dụng mô hình PCA để giảm kích thước dữ liệu
+ Áp dụng mô hình huấn luyện
+ Áp dụng mô hình để dự đoán dữ liệu mới
