---
title: "CloudWatch Logs"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>7.1. </b>"
---

## Thiết lập CloudWatch Logs

### Cấu hình Nhóm Log
[Chèn ảnh: Thiết lập nhóm log CloudWatch]
1. Tạo Nhóm Log
   ```bash
   aws logs create-log-group --log-group-name /aws/codebuild/test-automation
   aws logs put-retention-policy --log-group-name /aws/codebuild/test-automation --retention-in-days 30
   ```
   [Chèn ảnh: Tạo nhóm log]

2. Cấu hình Luồng Log
   [Chèn ảnh: Thiết lập luồng log]
   - Log build
   - Log thực thi kiểm thử
   - Chỉ số hiệu năng

### Thiết lập Chỉ số
[Chèn ảnh: Cấu hình chỉ số]
1. Tạo Bộ lọc Chỉ số
   ```bash
   aws logs put-metric-filter \
     --log-group-name /aws/codebuild/test-automation \
     --filter-name test-duration \
     --filter-pattern "[timestamp, duration]" \
     --metric-transformations \
         metricName=TestDuration,metricNamespace=TestAutomation,metricValue=$duration
   ```
   [Chèn ảnh: Tạo bộ lọc chỉ số]

2. Cấu hình Bảng điều khiển
   [Chèn ảnh: Thiết lập bảng điều khiển]
   - Chỉ số chi phí
   - Sử dụng tài nguyên
   - Thống kê thực thi kiểm thử

### Thiết lập Cảnh báo
[Chèn ảnh: Cấu hình cảnh báo]
1. Tạo Cảnh báo CloudWatch
   - Ngưỡng chi phí
   - Giới hạn tài nguyên
   - Tỷ lệ lỗi
   [Chèn ảnh: Tạo cảnh báo]

2. Cấu hình Thông báo
   [Chèn ảnh: Thiết lập thông báo]
   - Cảnh báo email
   - Chủ đề SNS
   - Webhook tích hợp

### Danh sách Xác minh
- [ ] Nhóm log đã tạo
- [ ] Chỉ số đã cấu hình
- [ ] Bảng điều khiển đã thiết lập
- [ ] Cảnh báo hoạt động
- [ ] Chính sách lưu giữ đã đặt

### Hướng dẫn Xử lý Sự cố
[Chèn ảnh: Vấn đề logging phổ biến]
1. Vấn đề Thu thập Log
   - Thiếu log
   - Gửi chậm
   - Vấn đề quyền

2. Vấn đề Chỉ số
   - Khớp bộ lọc
   - Tổng hợp dữ liệu
   - Lỗi tính toán

3. Vấn đề Cảnh báo
   - Gửi thông báo
   - Cài đặt ngưỡng
   - Lỗi tích hợp

### Thực hành Tốt nhất
[Chèn ảnh: Thực hành tốt nhất logging]
1. Quản lý Log
   - Logging có cấu trúc
   - Danh mục rõ ràng
   - Lưu giữ phù hợp

2. Cấu hình Chỉ số
   - Chỉ số liên quan
   - Tổng hợp phù hợp
   - Chiều hữu ích

### Bước tiếp theo
Sau khi thiết lập CloudWatch logs, tiếp tục với [Phân tích Chi phí](../7.2-analyze-cost/)
