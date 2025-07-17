---
title: "Kiểm thử Bảo mật"
date: 2025-07-04
weight: 6
chapter: false
pre: "<b>6. </b>"
---

## Tổng quan về Kiểm thử Bảo mật

Module này tập trung vào việc triển khai kiểm thử bảo mật trong pipeline CI/CD sử dụng AWS CodeBuild và CodeQL. Bạn sẽ học cách xác định lỗ hổng bảo mật, phân tích mã nguồn để tìm các vấn đề bảo mật tiềm ẩn và triển khai các thực hành bảo mật tốt nhất.

### Những gì Bạn sẽ Học

1. Kích hoạt Phân tích CodeQL
   - Thiết lập cấu hình
   - Hỗ trợ ngôn ngữ
   - Lựa chọn truy vấn
   - Thiết lập tích hợp

2. Xem xét Cảnh báo Bảo mật
   - Phân tích cảnh báo
   - Mức độ nghiêm trọng
   - Xử lý cảnh báo sai
   - Ưu tiên xử lý

3. Sửa Vấn đề Bảo mật
   - Khắc phục lỗ hổng
   - Cải thiện mã nguồn
   - Mẫu bảo mật
   - Thực hành tốt nhất

4. Cấu hình Cài đặt Bảo mật
   - Cấu hình cảnh báo
   - Lập lịch quét
   - Kiểm soát truy cập
   - Thiết lập báo cáo

### Yêu cầu Tiên quyết

Trước khi bắt đầu module này, đảm bảo bạn có:
- Hoàn thành Module 5 (Kiểm thử Hiệu năng)
- Hiểu biết về khái niệm bảo mật
- Quyền truy cập GitHub repository
- Cấu hình AWS CodeBuild

### Ước tính Thời gian
- Tổng thời gian Module: ~2.5 giờ
- Thời gian mỗi Phần: 35-40 phút

### Cấu trúc Module

1. [Kích hoạt CodeQL](6.1-enable-codeql/)
   - Thiết lập cấu hình
   - Thiết lập tích hợp

2. [Xem xét Cảnh báo](6.2-review-alerts/)
   - Phân tích cảnh báo
   - Ưu tiên vấn đề

3. [Sửa Lỗ hổng](6.3-fix-vulnerabilities/)
   - Khắc phục vấn đề
   - Cải thiện bảo mật

4. [Cấu hình Cài đặt](6.4-disable-if-needed/)
   - Cấu hình bảo mật
   - Quản lý quét

### Kết quả Mong đợi

Đến cuối module này, bạn sẽ có:
- Cấu hình phân tích CodeQL
- Triển khai quét bảo mật
- Xem xét cảnh báo bảo mật
- Sửa lỗ hổng bảo mật
- Quản lý cài đặt bảo mật

Hãy bắt đầu với [Kích hoạt CodeQL](6.1-enable-codeql/)!
