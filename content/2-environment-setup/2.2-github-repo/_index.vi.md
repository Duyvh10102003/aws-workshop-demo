---
title: "Thiết lập GitHub Repository"
date: 2025-07-04
weight: 2
chapter: false
pre: "<b>2.2. </b>"
---

## Thiết lập GitHub Repository

### Tạo Repository
[Chèn ảnh: Trang tạo repository mới trên GitHub]
1. Đăng nhập GitHub
   - Truy cập github.com
   - Nhấp vào biểu tượng "+" ở góc trên bên phải
   - Chọn "New repository"
   [Chèn ảnh: Nút tạo repository mới được đánh dấu]

2. Cấu hình Repository
   [Chèn ảnh: Form cài đặt repository]
   - Tên: `dotnet-test-automation`
   - Mô tả: "AWS CodeBuild Test Automation Demo"
   - Hiển thị: Public
   - Khởi tạo với README: Không
   [Chèn ảnh: Tùy chọn cấu hình được đánh dấu]

### Khởi tạo Repository Cục bộ
[Chèn ảnh: Terminal VS Code với lệnh git]
1. Mở thư mục dự án trong terminal
2. Khởi tạo git:
   ```bash
   git init
   git branch -M main
   ```

### Kết nối với GitHub
[Chèn ảnh: Vị trí URL repository trên GitHub]
1. Thêm remote:
   ```bash
   git remote add origin https://github.com/<tên-người-dùng>/dotnet-test-automation.git
   ```

2. Đẩy code:
   ```bash
   git add .
   git commit -m "Initial commit"
   git push -u origin main
   ```
   [Chèn ảnh: Kết quả push thành công]

### Bảo vệ Nhánh
[Chèn ảnh: Trang cài đặt bảo vệ nhánh]
1. Vào Settings của repository
2. Chọn Branches
3. Thêm quy tắc cho `main`:
   - Yêu cầu đánh giá pull request
   - Yêu cầu kiểm tra trạng thái
   - Áp dụng cho cả quản trị viên
   [Chèn ảnh: Cấu hình quy tắc bảo vệ]

### Danh sách Xác minh
- [ ] Repository đã tạo thành công
- [ ] Repository cục bộ đã khởi tạo
- [ ] Code đã đẩy lên GitHub
- [ ] Bảo vệ nhánh đã cấu hình
- [ ] Có thể xem code trên GitHub

### Hướng dẫn Xử lý Sự cố
[Chèn ảnh: Lỗi GitHub phổ biến và giải pháp]
1. Vấn đề Xác thực
   - Kiểm tra thông tin đăng nhập GitHub
   - Xác minh khóa SSH
   - Sử dụng token truy cập cá nhân

2. Lỗi Push
   - Kiểm tra URL remote
   - Xác minh tên nhánh
   - Giải quyết xung đột

3. Vấn đề Quyền
   - Xác minh quyền truy cập repository
   - Kiểm tra quyền người dùng
   - Xem xét cài đặt tổ chức

### Bước tiếp theo
Sau khi thiết lập GitHub repository, tiếp tục với [Cài đặt Công cụ Cần thiết](../2.3-install-tools/)
