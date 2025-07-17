---
title: "Cài đặt Công cụ Cần thiết"
date: 2025-07-04
weight: 3
chapter: false
pre: "<b>2.3. </b>"
---

## Cài đặt Công cụ Cần thiết

### Cài đặt AWS CLI
[Chèn ảnh: Trang tải AWS CLI]
1. Tải AWS CLI
   - Windows: Tải trình cài đặt MSI
   - Linux/macOS: Sử dụng trình quản lý gói
   [Chèn ảnh: Tùy chọn tải xuống được đánh dấu]

2. Cài đặt AWS CLI
   [Chèn ảnh: Các bước cài đặt]
   - Chạy trình cài đặt
   - Chấp nhận điều khoản
   - Chọn vị trí cài đặt
   - Hoàn thành cài đặt

3. Xác minh Cài đặt
   [Chèn ảnh: Terminal hiển thị kiểm tra phiên bản]
   ```bash
   aws --version
   ```

### Cấu hình AWS Credentials
[Chèn ảnh: Trang thông tin xác thực AWS IAM console]
1. Lấy Access Keys
   - Mở AWS Console
   - Đi tới IAM
   - Tạo access key
   [Chèn ảnh: Quy trình tạo access key]

2. Cấu hình CLI
   [Chèn ảnh: Lệnh aws configure]
   ```bash
   aws configure
   ```
   Nhập:
   - AWS Access Key ID
   - AWS Secret Access Key
   - Vùng mặc định
   - Định dạng đầu ra

### Cài đặt VS Code Extensions
[Chèn ảnh: Marketplace tiện ích mở rộng VS Code]
1. Tiện ích Cần thiết:
   - AWS Toolkit
   - C# Dev Kit
   - .NET Core Test Explorer
   [Chèn ảnh: Nút cài đặt tiện ích]

2. Cấu hình Tiện ích
   [Chèn ảnh: Cài đặt tiện ích]
   - Cài đặt AWS Toolkit
   - Cấu hình C#
   - Thiết lập Test Explorer

### Danh sách Xác minh
- [ ] AWS CLI đã cài đặt
- [ ] AWS credentials đã cấu hình
- [ ] VS Code extensions đã cài đặt
- [ ] Có thể chạy lệnh AWS CLI
- [ ] Có thể truy cập dịch vụ AWS

### Hướng dẫn Xử lý Sự cố
[Chèn ảnh: Vấn đề cài đặt phổ biến]
1. Vấn đề AWS CLI
   - Không tìm thấy đường dẫn
   - Lỗi quyền
   - Lỗi thông tin xác thực

2. Vấn đề VS Code
   - Xung đột tiện ích
   - Vấn đề tải
   - Yêu cầu cập nhật

3. Vấn đề Truy cập AWS
   - Thông tin xác thực không hợp lệ
   - Từ chối quyền
   - Vấn đề vùng

### Thực hành Tốt nhất
[Chèn ảnh: Thực hành bảo mật AWS tốt nhất]
1. Bảo mật
   - Sử dụng vai trò IAM
   - Xoay vòng access keys
   - Quyền tối thiểu

2. Cấu hình
   - Hồ sơ có tên
   - Cài đặt vùng
   - Định dạng đầu ra mặc định

### Bước tiếp theo
Sau khi cài đặt tất cả công cụ cần thiết, tiếp tục với [Thiết lập Dự án CodeBuild](../2.4-codebuild-project/)
