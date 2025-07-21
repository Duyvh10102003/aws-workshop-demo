---
title: "Tích hợp vào CI/CD"
date: 2025-07-04
weight: 2
chapter: false
pre: "<b>5.2. </b>"
---

## Tích hợp Kiểm thử Hiệu năng vào CI/CD

### Cấu hình Pipeline Build
[Chèn ảnh: Cấu hình CodeBuild]
1. Cập nhật BuildSpec
   ```yaml
   version: 0.2
   phases:
     install:
       commands:
         - curl -L https://github.com/grafana/k6/releases/download/v0.45.0/k6-v0.45.0-linux-amd64.tar.gz | tar xvz
         - mv k6-v0.45.0-linux-amd64/k6 /usr/local/bin
     build:
       commands:
         - k6 run performance-tests/load-test.js
   ```
   [Chèn ảnh: Cấu hình BuildSpec]

2. Thiết lập Môi trường
   [Chèn ảnh: Thiết lập môi trường]
   - Cấu hình tài nguyên
   - Đặt biến
   - Xác định giới hạn

### Triển khai Tự động hóa Kiểm thử
[Chèn ảnh: Thiết lập tự động hóa kiểm thử]
1. Tạo Quy trình Kiểm thử
   - Điều kiện kích hoạt
   - Trình tự kiểm thử
   - Xử lý kết quả
   [Chèn ảnh: Cấu hình quy trình]

2. Cấu hình Tài nguyên
   [Chèn ảnh: Cấu hình tài nguyên]
   - Yêu cầu tính toán
   - Phân bổ bộ nhớ
   - Cài đặt mạng

### Thiết lập Giám sát
[Chèn ảnh: Thiết lập giám sát]
1. Cấu hình CloudWatch
   - Thu thập chỉ số
   - Tạo bảng điều khiển
   - Cấu hình cảnh báo
   [Chèn ảnh: Cài đặt CloudWatch]

2. Thiết lập Thông báo
   [Chèn ảnh: Thiết lập thông báo]
   - Ngưỡng cảnh báo
   - Kênh thông báo
   - Hành động phản hồi

### Danh sách Xác minh
- [ ] Pipeline đã cấu hình
- [ ] Kiểm thử đã tự động hóa
- [ ] Tài nguyên đã phân bổ
- [ ] Giám sát đang hoạt động
- [ ] Thông báo hoạt động

### Hướng dẫn Xử lý Sự cố
[Chèn ảnh: Vấn đề tích hợp phổ biến]
1. Vấn đề Pipeline
   - Lỗi build
   - Vấn đề tài nguyên
   - Lỗi cấu hình

2. Thực thi Kiểm thử
   - Vấn đề thời gian
   - Hạn chế tài nguyên
   - Vấn đề mạng

3. Vấn đề Giám sát
   - Thu thập dữ liệu
   - Kích hoạt cảnh báo
   - Cập nhật bảng điều khiển

### Thực hành Tốt nhất
[Chèn ảnh: Thực hành tốt nhất tích hợp]
1. Cấu hình Pipeline
   - Giai đoạn rõ ràng
   - Tài nguyên phù hợp
   - Xử lý lỗi

2. Quản lý Kiểm thử
   - Thực thi thường xuyên
   - Theo dõi kết quả
   - Giám sát hiệu năng

### Bước tiếp theo
Sau khi tích hợp với CI/CD, tiếp tục với [Xuất Kết quả](../5.3-export-results/)
