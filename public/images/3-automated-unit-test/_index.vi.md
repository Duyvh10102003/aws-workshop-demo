---
title: "Kiểm thử Đơn vị Tự động"
date: 2025-07-04
weight: 3
chapter: false
pre: "<b>3. </b>"
---

## Tổng quan về Kiểm thử Đơn vị Tự động

Module này tập trung vào việc triển khai kiểm thử đơn vị tự động trong pipeline CI/CD sử dụng AWS CodeBuild. Bạn sẽ học cách viết các bài kiểm thử đơn vị hiệu quả, cấu hình tự động hóa kiểm thử và tích hợp kết quả kiểm thử vào quy trình phát triển.

### Những gì Bạn sẽ Học

1. Viết Kiểm thử Đơn vị
   - Tạo dự án kiểm thử
   - Viết các ca kiểm thử hiệu quả
   - Triển khai các mẫu kiểm thử
   - Sử dụng framework xUnit

2. Cấu hình BuildSpec
   - Cấu hình thực thi kiểm thử
   - Thiết lập báo cáo kiểm thử
   - Quản lý các phụ thuộc kiểm thử

3. Đẩy và Kích hoạt Kiểm thử
   - Tự động hóa thực thi kiểm thử
   - Cấu hình kích hoạt build
   - Quản lý quy trình kiểm thử

4. Xem Kết quả Kiểm thử
   - Phân tích báo cáo kiểm thử
   - Diễn giải số liệu kiểm thử
   - Theo dõi độ bao phủ kiểm thử

5. Sửa Lỗi Kiểm thử
   - Gỡ lỗi các kiểm thử thất bại
   - Triển khai sửa chữa
   - Xác nhận các sửa đổi

### Yêu cầu Tiên quyết

Trước khi bắt đầu module này, đảm bảo bạn có:
- Hoàn thành Module 2 (Thiết lập Môi trường)
- Hiểu biết về kiểm thử C# và .NET
- Quen thuộc với framework xUnit
- Quyền truy cập dự án AWS CodeBuild

### Ước tính Thời gian
- Tổng thời gian Module: ~2.5 giờ
- Thời gian mỗi Phần: 30 phút

### Cấu trúc Module

1. [Viết Kiểm thử Đơn vị](3.1-write-unit-tests/)
   - Thiết lập dự án kiểm thử
   - Triển khai ca kiểm thử

2. [Thiết lập BuildSpec](3.2-buildspec-setup/)
   - Cấu hình build
   - Thiết lập tự động hóa kiểm thử

3. [Đẩy và Kích hoạt](3.3-push-trigger/)
   - Thực thi tự động
   - Tích hợp pipeline

4. [Xem Kết quả](3.4-view-results/)
   - Phân tích kết quả
   - Diễn giải báo cáo

5. [Sửa Lỗi](3.5-fix-failures/)
   - Xử lý sự cố
   - Sửa chữa triển khai

### Kết quả Mong đợi

Đến cuối module này, bạn sẽ có:
- Một bộ kiểm thử đơn vị toàn diện
- Thực thi kiểm thử tự động trong CI/CD
- Báo cáo và phân tích kết quả kiểm thử
- Kinh nghiệm sửa lỗi kiểm thử
- Quy trình chất lượng mã nguồn được cải thiện

Hãy bắt đầu với [Viết Kiểm thử Đơn vị](3.1-write-unit-tests/)!
