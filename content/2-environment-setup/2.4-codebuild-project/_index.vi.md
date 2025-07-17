---
title: "Thiết lập Dự án CodeBuild"
date: 2025-07-04
weight: 4
chapter: false
pre: "<b>2.4. </b>"
---

## Thiết lập Dự án AWS CodeBuild

### Tạo Dự án CodeBuild
[Chèn ảnh: Bảng điều khiển AWS CodeBuild]
1. Mở AWS Console
   - Đi tới dịch vụ CodeBuild
   - Nhấp "Create build project"
   [Chèn ảnh: Nút tạo dự án]

2. Cấu hình Dự án
   [Chèn ảnh: Form cài đặt dự án]
   - Tên dự án: `dotnet-test-automation`
   - Nhà cung cấp nguồn: GitHub
   - Repository: Chọn repository của bạn
   [Chèn ảnh: Cài đặt nguồn được đánh dấu]

3. Thiết lập Môi trường
   [Chèn ảnh: Cấu hình môi trường]
   - Hệ điều hành: Ubuntu
   - Runtime: Standard
   - Image: aws/codebuild/amazonlinux2-x86_64-standard:4.0
   [Chèn ảnh: Tùy chọn môi trường]

### Cấu hình Cài đặt Build
[Chèn ảnh: Trang cấu hình build]
1. Tạo buildspec.yml
   - Cấu hình cơ bản được hiển thị bên dưới
   - Cấu hình đầy đủ trong module tiếp theo
   ```yaml
   version: 0.2
   phases:
     install:
       runtime-versions:
         dotnet: 8.0
     build:
       commands:
         - dotnet build
         - dotnet test
   ```

2. Cấu hình Artifacts
   [Chèn ảnh: Cài đặt artifacts]
   - Loại: Không có artifacts
   - Bật logs trong CloudWatch

### Thiết lập Vai trò IAM
[Chèn ảnh: Tạo vai trò IAM]
1. Tạo Service Role
   - Vai trò sẽ được tạo tự động
   - Xem xét quyền
   - Thêm quyền bổ sung nếu cần

### Danh sách Xác minh
- [ ] Dự án đã tạo thành công
- [ ] Kết nối GitHub hoạt động
- [ ] Môi trường đã cấu hình
- [ ] Vai trò IAM đã tạo
- [ ] Build cơ bản thành công

### Hướng dẫn Xử lý Sự cố
[Chèn ảnh: Vấn đề CodeBuild phổ biến]
1. Vấn đề Kết nối GitHub
   - Kiểm tra token OAuth
   - Xác minh quyền
   - Xem xét trạng thái kết nối

2. Lỗi Build
   - Kiểm tra cú pháp buildspec
   - Xác minh môi trường
   - Xem xét quyền IAM

3. Vấn đề Môi trường
   - Tương thích image
   - Giới hạn tài nguyên
   - Phiên bản runtime

### Thực hành Tốt nhất
[Chèn ảnh: Thực hành tốt nhất CodeBuild]
1. Bảo mật
   - Quyền IAM tối thiểu
   - Biến môi trường an toàn
   - Cập nhật thường xuyên

2. Hiệu năng
   - Kích thước compute phù hợp
   - Cấu hình cache
   - Tối ưu hóa build

### Bước tiếp theo
Sau khi thiết lập CodeBuild, tiếp tục với [Xác minh Webhook](../2.5-webhook-verify/)
