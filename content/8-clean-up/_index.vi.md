---
title: "Dọn dẹp Tài nguyên"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>8.1. </b>"
---

## Dọn dẹp Tài nguyên Workshop

### Chuẩn bị Dọn dẹp
[Chèn ảnh: Chuẩn bị dọn dẹp]
1. Tạo Danh sách Tài nguyên
   ```bash
   # Liệt kê tài nguyên AWS
   aws resourcegroupstaggingapi get-resources \
     --tag-filters Key=Project,Values=test-automation
   ```
   [Chèn ảnh: Liệt kê tài nguyên]

2. Xác minh Phụ thuộc Tài nguyên
   [Chèn ảnh: Xác minh phụ thuộc]
   - Phụ thuộc dịch vụ
   - Quan hệ tài nguyên
   - Phụ thuộc dữ liệu

### Xóa Tài nguyên AWS
[Chèn ảnh: Xóa tài nguyên]
1. Xóa Tài nguyên CodeBuild
   ```bash
   # Xóa dự án CodeBuild
   aws codebuild delete-project --name test-automation
   
   # Xóa bucket artifacts
   aws s3 rm s3://test-artifacts-bucket --recursive
   aws s3 rb s3://test-artifacts-bucket
   ```
   [Chèn ảnh: Dọn dẹp CodeBuild]

2. Dọn dẹp Tài nguyên CloudWatch
   ```bash
   # Xóa nhóm log
   aws logs delete-log-group --log-group-name /aws/codebuild/test-automation
   
   # Xóa bảng điều khiển
   aws cloudwatch delete-dashboards --dashboard-names test-automation
   ```
   [Chèn ảnh: Dọn dẹp CloudWatch]

### Xác minh Dọn dẹp
[Chèn ảnh: Xác minh dọn dẹp]
1. Kiểm tra Trạng thái Tài nguyên
   - Xác minh xóa
   - Kiểm tra tài nguyên còn lại
   - Xác nhận dọn dẹp
   [Chèn ảnh: Kiểm tra trạng thái]

2. Xem xét Tác động Thanh toán
   [Chèn ảnh: Xem xét thanh toán]
   - Kiểm tra phí hiện tại
   - Xác minh chấm dứt tài nguyên
   - Theo dõi hóa đơn cuối cùng

### Danh sách Xác minh
- [ ] Tài nguyên đã xác định
- [ ] Phụ thuộc đã giải quyết
- [ ] Tài nguyên đã xóa
- [ ] Dọn dẹp đã xác minh
- [ ] Thanh toán đã kiểm tra

### Hướng dẫn Xử lý Sự cố
[Chèn ảnh: Vấn đề dọn dẹp phổ biến]
1. Vấn đề Xóa
   - Khóa tài nguyên
   - Vấn đề quyền
   - Xung đột phụ thuộc

2. Vấn đề Xác minh
   - Tài nguyên ẩn
   - Xóa chậm
   - Cập nhật thanh toán

3. Vấn đề Phụ thuộc
   - Kết nối dịch vụ
   - Liên kết tài nguyên
   - Quan hệ dữ liệu

### Thực hành Tốt nhất
[Chèn ảnh: Thực hành tốt nhất dọn dẹp]
1. Quản lý Tài nguyên
   - Xóa có hệ thống
   - Xử lý phụ thuộc
   - Các bước xác minh

2. Tài liệu hóa
   - Theo dõi tài nguyên
   - Quy trình dọn dẹp
   - Giải quyết vấn đề

### Bước Cuối cùng
Sau khi dọn dẹp, xác minh tất cả tài nguyên đã được xóa và không có phí bất ngờ phát sinh.
