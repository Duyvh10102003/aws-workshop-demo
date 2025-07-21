---
title: "Thiết lập BuildSpec"
date: 2025-07-04
weight: 2
chapter: false
pre: "<b>3.2. </b>"
---

## Thiết lập BuildSpec cho Tự động hóa Kiểm thử

### Tạo File BuildSpec
[Chèn ảnh: Tạo buildspec.yml trong VS Code]
1. Tạo buildspec.yml
   - Tạo trong thư mục gốc dự án
   - Sử dụng cấu trúc cơ bản bên dưới
   [Chèn ảnh: Cấu trúc buildspec cơ bản]

2. Cấu hình Cơ bản
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
   [Chèn ảnh: BuildSpec với phần được đánh dấu]

### Cấu hình Cài đặt Kiểm thử
[Chèn ảnh: Cấu hình cài đặt kiểm thử]
1. Thêm Tùy chọn Kiểm thử
   - Logger kiểm thử
   - Thư mục kết quả
   - Thu thập độ bao phủ
   [Chèn ảnh: Tùy chọn cấu hình kiểm thử]

2. Cấu hình Báo cáo
   [Chèn ảnh: Cấu hình báo cáo]
   - Định dạng TRX
   - Báo cáo độ bao phủ
   - Báo cáo tùy chỉnh

### Thiết lập Artifacts
[Chèn ảnh: Cấu hình artifacts]
1. Cấu hình Đầu ra
   - Kết quả kiểm thử
   - Báo cáo độ bao phủ
   - File log
   [Chèn ảnh: Cài đặt artifacts]

### Danh sách Xác minh
- [ ] File BuildSpec đã tạo
- [ ] Cấu hình kiểm thử đã thêm
- [ ] Báo cáo đã cấu hình
- [ ] Artifacts đã thiết lập
- [ ] Cú pháp đã xác thực

### Hướng dẫn Xử lý Sự cố
[Chèn ảnh: Vấn đề BuildSpec phổ biến]
1. Lỗi Cú pháp
   - Kiểm tra định dạng YAML
   - Xác minh thụt lề
   - Xác thực cấu hình

2. Lỗi Build
   - Kiểm tra thứ tự phase
   - Xác minh lệnh
   - Xem xét môi trường

3. Vấn đề Báo cáo
   - Kiểm tra đường dẫn
   - Xác minh quyền
   - Xem xét định dạng

### Thực hành Tốt nhất
[Chèn ảnh: Thực hành tốt nhất BuildSpec]
1. Tổ chức File
   - Cấu trúc rõ ràng
   - Thụt lề phù hợp
   - Tùy chọn có tài liệu

2. Cấu hình
   - Biến môi trường
   - Bước có điều kiện
   - Xử lý lỗi

### Bước tiếp theo
Sau khi thiết lập BuildSpec, tiếp tục với [Đẩy và Kích hoạt](../3.3-push-trigger/)
