# PHẦN 1 : 
## 1. Phân biệt Yêu cầu Chức năng & Phi chức năng
### 1.1 Yêu cầu Chức năng 

- Tạo mới/Cập nhật bệnh án: Cho phép bác sĩ nhập thông tin khám, chẩn đoán, kê đơn thuốc và chỉ định cận lâm sàng.

- Lịch sử khám bệnh: Truy xuất lịch sử khám, kết quả xét nghiệm và đơn thuốc cũ của bệnh nhân theo mã ID.

Tra cứu & Lọc dữ liệu: Tìm kiếm bệnh nhân theo tên, mã BHYT, số điện thoại hoặc lọc theo danh mục bệnh lý.
### 1.2 Yêu cầu Phi chức năng 

- Bảo mật dữ liệu y tế (HIPAA / ISO 27001): Mã hóa dữ liệu nhạy cảm (họ tên, CMND/CCCD, địa chỉ, chẩn đoán) ở trạng thái lưu trữ (Encryption at Rest - AES-256) và trên đường truyền (Encryption in Transit - TLS 1.3).

- Phân quyền truy cập (RBAC): Bác sĩ chỉ xem/sửa bệnh án của bệnh nhân đang điều trị; Lễ tân chỉ thấy thông tin hành chính; Dược sĩ chỉ xem đơn thuốc.
# PHẦN 2: TRIỂN KHAI HỆ THỐNG & QUẢN LÝ DỮ LIỆU EXCEL
Giải pháp xử lý bẫy hàng nghìn ô trống làm đứt gãy AutoFilter
- Cách 1: Chuyển vùng dữ liệu thành Excel Table (Ctrl + T) — Khuyên dùngQuét chọn toàn bộ vùng dữ liệu từ dòng tiêu đề đến dòng cuối cùng (ví dụ: A1:H1001).Nhấn tổ hợp phím Ctrl + T (tích chọn My table has headers) $\rightarrow$ Chuyển thành Table.Tác dụng: Excel Table tự động coi toàn bộ khối dữ liệu là một thể thống nhất. Tính năng AutoFilter trên Header của Table sẽ quét xuống hết dòng cuối cùng bất chấp bên trong có bao nhiêu ô trống.
- Cách 2: Định danh chuẩn dữ liệu mặc định (Data Clean)Điền giá trị mặc định cho ô thiếu thông tin: N/A, Chưa cập nhật, hoặc 0 tùy loại dữ liệu.Sử dụng phím tắt: Chọn vùng dữ liệu $\rightarrow$ Nhấn F5 (hoặc Ctrl + G) $\rightarrow$ Chọn Special... $\rightarrow$ Chọn Blanks $\rightarrow$ Nhập "Chưa cập nhật" $\rightarrow$ Nhấn Ctrl + Enter để điền hàng loạt vào các ô trốn
# KIỂM THỬ & SỬA LỖI ĐỊNH DẠNG DOCUMENT (WORD)
- Bước 1: Bật thanh Navigation Pane (Ctrl + F $\rightarrow$ chọn thẻ Headings) để phát hiện các đoạn văn bản bị biến thành tiêu đề nhầm.
- Bước 2: Bôi đen (chọn) đoạn văn bản đang bị lỗi định dạng Heading.
- Bước 3: Nhấn tổ hợp phím Ctrl + Shift + N.
- Bước 4 (Kế thừa định dạng): Đoạn văn bản sẽ lập tức quay về Style Normal, loại bỏ khỏi danh sách Heading và Mục lục tự động. Nếu cần định dạng lại phông chữ/căn lề thủ công, thực hiện căn chỉnh theo quy chuẩn văn bản mà không lo bị dính lỗi tổ chức cây tiêu đề.
