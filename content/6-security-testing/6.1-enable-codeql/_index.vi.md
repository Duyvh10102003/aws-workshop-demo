---
title: "Kích hoạt CodeQL"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>6.1. </b>"
---

## Kích hoạt Phân tích CodeQL

### Thiết lập Môi trường CodeQL
[Chèn ảnh: Thiết lập CodeQL]
1. Cấu hình GitHub Repository
   - Kích hoạt GitHub Actions
   - Cấu hình cài đặt bảo mật
   - Thiết lập quyền
   [Chèn ảnh: Cấu hình GitHub]

2. Tạo Workflow CodeQL
   ```yaml
   name: "Phân tích CodeQL"
   
   on:
     push:
       branches: [ main ]
     pull_request:
       branches: [ main ]
     schedule:
       - cron: '0 0 * * 0'
   
   jobs:
     analyze:
       runs-on: ubuntu-latest
       steps:
         - name: Checkout code
           uses: actions/checkout@v2
         
         - name: Initialize CodeQL
           uses: github/codeql-action/init@v2
           with:
             languages: csharp
   ```
   [Chèn ảnh: Cấu hình workflow]

### Cấu hình Cài đặt Phân tích
[Chèn ảnh: Cấu hình phân tích]
1. Thiết lập Bộ Truy vấn
   - Chọn truy vấn bảo mật
   - Cấu hình truy vấn tùy chỉnh
   - Đặt phạm vi phân tích
   [Chèn ảnh: Cấu hình truy vấn]

2. Cấu hình Tích hợp Build
   [Chèn ảnh: Tích hợp build]
   - Cài đặt build
   - Kích hoạt phân tích
   - Xử lý kết quả

### Thiết lập Thông báo
[Chèn ảnh: Thiết lập thông báo]
1. Cấu hình Cảnh báo
   - Cảnh báo bảo mật
   - Thông báo workflow
   - Thông báo nhóm
   [Chèn ảnh: Cấu hình cảnh báo]

### Danh sách Xác minh
- [ ] CodeQL đã kích hoạt
- [ ] Workflow đã cấu hình
- [ ] Truy vấn đã chọn
- [ ] Thông báo đã thiết lập
- [ ] Tích hợp đã kiểm thử

### Hướng dẫn Xử lý Sự cố
[Chèn ảnh: Vấn đề CodeQL phổ biến]
1. Vấn đề Thiết lập
   - Vấn đề quyền
   - Lỗi cấu hình
   - Lỗi tích hợp

2. Vấn đề Phân tích
   - Lỗi build
   - Lỗi truy vấn
   - Hạn chế tài nguyên

3. Vấn đề Thông báo
   - Gửi cảnh báo
   - Vấn đề cấu hình
   - Quyền truy cập

### Thực hành Tốt nhất
[Chèn ảnh: Thực hành tốt nhất CodeQL]
1. Cấu hình
   - Cập nhật thường xuyên
   - Tài liệu rõ ràng
   - Phạm vi phù hợp

2. Quản lý Phân tích
   - Xem xét thường xuyên
   - Giám sát hiệu năng
   - Theo dõi kết quả

### Bước tiếp theo
Sau khi kích hoạt CodeQL, tiếp tục với [Xem xét Cảnh báo](../6.2-review-alerts/)
