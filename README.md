# Python Data Cleaning Project (FIFA21 Dataset)

### Giới thiệu

Kho lưu trữ này chứa mã và tài liệu cho quy trình làm sạch dữ liệu của bộ dữ liệu FIFA21. 
Mục tiêu của dự án này là làm sạch và cải thiện bộ dữ liệu cung cấp thông tin về cầu thủ trong trò chơi điện tử nổi tiếng FIFA21.

### Nguồn dữ liệu và tổng quan

Bộ dữ liệu FIFA 21 được sử dụng trong dự án này được lấy từ một thử thách làm sạch dữ liệu trên Twitter mà tôi đã tham gia.
Nó bao gồm các thuộc tính của cầu thủ, số liệu thống kê và các thông tin liên quan khác.

Bộ dữ liệu gốc của FIFA21 chứa hơn 18.000 bản ghi dữ liệu cầu thủ. Mỗi bản ghi đại diện cho một cầu thủ duy nhất và bao gồm
các thuộc tính khác nhau như tên, tuổi, quốc tịch, câu lạc bộ, xếp hạng tổng thể, v.v..

### Các vấn đề được tìm thấy trong dữ liệu

Trong quá trình khám phá và phân tích ban đầu bộ dữ liệu FIFA21, một số vấn đề đã được xác định bao gồm:

- Missing values - Các cột Số lần truy cập (Hits) và Ngày kết thúc cho vay (Loan Date End) có các giá trị bị thiếu cần xử lý và tính toán cẩn thận.
- Inconsistent formatting - Điều này được quan sát thấy trên các cột khác nhau nên cần phải chuẩn hóa dữ liệu để đảm bảo tính nhất quán. 
Mỗi cột Chiều cao và Cân nặng có các giá trị được lưu trữ ở các đơn vị khác nhau.

### Các công cụ được sử dụng

1. **Python** cho các tác vụ data cleaning.
2. **Pandas** cho data manipulation, cleaning và xử lý missing values.
3. **NumPy** được dùng cho mathematical operations và array handling trong quá trình data cleaning.

### Quy trình thực hiện Data Cleaning 

1. **Data Understanding** - Tập dữ liệu đã được kiểm tra kỹ lưỡng để hiểu cấu trúc, các cột và ý nghĩa của chúng.
   Dữ liệu không có từ điển dữ liệu kèm theo. Với sự trợ giúp của các nguồn trực tuyến, tôi đã có thể tạo một nguồn 
   giúp tôi hiểu được ý nghĩa của tất cả các cột.
2. **Data Exploration** - Phân tích dữ liệu khám phá (EDA) đã được thực hiện để hiểu rõ hơn về dữ liệu, xác định các mẫu và phát hiện ra sự bất thường.
3. **Handling missing values** - Thông qua EDA, tôi nhanh chóng nhận ra rằng có lý do chính đáng cho các giá trị bị thiếu trong cột Hits và Loan Date End.
   Cột Hits thể hiện số lần một cầu thủ được tìm kiếm trong cơ sở dữ liệu FIFA. Vì một số cầu thủ chưa bao giờ được tìm kiếm nên hồ sơ của họ trống (B).
   Đối với cột Loan Date End, cột này thể hiện thời điểm hợp đồng dành cho các cầu thủ *On Loan* sẽ kết thúc. Vì một số cầu thủ tự do và 
   những người khác còn hợp đồng nên hồ sơ của họ bị bỏ trống.
4. **Standardizing formatting** - Các vấn đề về định dạng không nhất quán, ví dụ: các giá trị trong cột Chiều cao và Trọng lượng được lưu trữ với các đơn vị khác nhau đã được giải quyết bằng cách áp dụng các phép biến đổi, hàm lambda và kỹ thuật chuẩn hóa dữ liệu
5. **Validation and quality checks** - Bộ dữ liệu đã được làm sạch trải qua quá trình xác thực nghiêm ngặt để đảm bảo chất lượng, độ chính xác và tính toàn vẹn của dữ liệu.