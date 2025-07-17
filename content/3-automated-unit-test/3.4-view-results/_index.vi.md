---
title: "Xem Kết quả"
date: 2025-07-04
weight: 4
chapter: false
pre: "<b>3.4. </b>"
---

## Xem Kết quả Kiểm thử

### Truy cập Kết quả Build
[Chèn ảnh: Trang kết quả CodeBuild]
1. Mở Chi tiết Build
   - Điều hướng đến CodeBuild
   - Chọn build mới nhất
   - Xem các giai đoạn build
   [Chèn ảnh: Trang chi tiết build]

2. Truy cập Báo cáo Kiểm thử
   [Chèn ảnh: Tab báo cáo kiểm thử]
   - Mở tab Reports
   - Xem tổng quan kiểm thử
   - Kiểm tra chi tiết kiểm thử

### Phân tích Kết quả Kiểm thử
[Chèn ảnh: Bảng điều khiển kết quả kiểm thử]
1. Xem xét Thống kê Kiểm thử
   - Tổng số kiểm thử đã chạy
   - Số lượng pass/fail
   - Thời gian kiểm thử
   [Chèn ảnh: Thống kê kiểm thử]

2. Kiểm tra Báo cáo Độ bao phủ
   [Chèn ảnh: Báo cáo độ bao phủ]
   - Chỉ số độ bao phủ mã
   - Xu hướng độ bao phủ
   - Vùng chưa được bao phủ

### Xem Log Chi tiết
[Chèn ảnh: Log CloudWatch]
1. Truy cập CloudWatch Logs
   - Tìm nhóm log
   - Chọn luồng log
   - Xem đầu ra kiểm thử
   [Chèn ảnh: Chi tiết log]

2. Xem xét Log Build
   [Chèn ảnh: Chi tiết log build]
   - Các bước build
   - Thực thi kiểm thử
   - Thông báo lỗi

### Danh sách Xác minh
- [ ] Build hoàn thành thành công
- [ ] Kết quả kiểm thử có thể truy cập
- [ ] Báo cáo độ bao phủ có sẵn
- [ ] Log có thể xem
- [ ] Chỉ số được ghi lại

### Hướng dẫn Xử lý Sự cố
[Chèn ảnh: Vấn đề xem thường gặp]
1. Vấn đề Truy cập
   - Kiểm tra quyền
   - Xác minh lưu giữ log
   - Xem xét vai trò IAM

2. Vấn đề Báo cáo
   - Kiểm tra tạo báo cáo
   - Xác minh artifacts
   - Xem xét định dạng

3. Vấn đề Log
   - Kiểm tra luồng log
   - Xác minh gửi log
   - Xem xét nhóm log

### Thực hành Tốt nhất
[Chèn ảnh: Thực hành tốt nhất xem kết quả]
1. Quản lý Kết quả
   - Giám sát thường xuyên
   - Phân tích xu hướng
   - Theo dõi vấn đề

2. Tài liệu hóa
   - Chụp ảnh kết quả
   - Ghi chép vấn đề
   - Theo dõi thay đổi

### Bước tiếp theo
Sau khi xem xét kết quả, tiếp tục với [Sửa Lỗi](../3.5-fix-failures/)
