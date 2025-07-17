---
title: "Xác minh Webhook"
date: 2025-07-04
weight: 5
chapter: false
pre: "<b>2.5. </b>"
---

## Xác minh Tích hợp Webhook

### Kiểm tra Cấu hình Webhook
[Chèn ảnh: Trang cài đặt webhook GitHub]
1. Truy cập Cài đặt Webhook
   - Vào cài đặt repository
   - Chọn Webhooks
   - Xác minh webhook CodeBuild tồn tại
   [Chèn ảnh: Danh sách webhook với webhook CodeBuild]

2. Xem xét Chi tiết Webhook
   [Chèn ảnh: Chi tiết cấu hình webhook]
   - URL đích
   - Loại nội dung
   - Mã bí mật
   - Xác minh SSL

### Kiểm tra Kích hoạt Webhook
[Chèn ảnh: Thực hiện commit kiểm tra]
1. Tạo Thay đổi Kiểm tra
   ```bash
   echo "# Test webhook" >> README.md
   git add README.md
   git commit -m "test: xác minh webhook"
   git push
   ```

2. Theo dõi Kích hoạt Build
   [Chèn ảnh: Bảng điều khiển CodeBuild hiển thị build được kích hoạt]
   - Theo dõi bảng điều khiển CodeBuild
   - Kiểm tra trạng thái build
   - Xem xét log build

### Xác minh Log Webhook
[Chèn ảnh: Log gửi webhook GitHub]
1. Kiểm tra Gửi Gần đây
   - Vào cài đặt webhook
   - Xem các lần gửi gần đây
   - Kiểm tra mã phản hồi
   [Chèn ảnh: Chi tiết gửi webhook]

2. Xem xét Chi tiết Phản hồi
   [Chèn ảnh: Chi tiết phản hồi webhook]
   - Headers
   - Payload
   - Phản hồi

### Danh sách Xác minh
- [ ] Webhook đã cấu hình đúng
- [ ] Commit kiểm tra kích hoạt build
- [ ] Build thực thi thành công
- [ ] Log webhook hiển thị gửi thành công
- [ ] Mã phản hồi là 200 OK

### Hướng dẫn Xử lý Sự cố
[Chèn ảnh: Vấn đề webhook phổ biến]
1. Vấn đề Kích hoạt
   - Kiểm tra trạng thái webhook
   - Xác minh quyền GitHub
   - Xem xét loại sự kiện

2. Vấn đề Build
   - Kiểm tra vai trò IAM
   - Xác minh cấu hình build
   - Xem xét giới hạn dịch vụ

3. Vấn đề Kết nối
   - Kiểm tra kết nối mạng
   - Xác minh cài đặt SSL
   - Xem xét nhóm bảo mật

### Thực hành Tốt nhất
[Chèn ảnh: Thực hành tốt nhất webhook]
1. Bảo mật
   - Sử dụng mã bí mật webhook
   - Bật xác minh SSL
   - Xoay vòng mã bí mật thường xuyên

2. Giám sát
   - Kiểm tra log gửi
   - Theo dõi thời gian phản hồi
   - Thiết lập thông báo

### Bước tiếp theo
Sau khi xác minh webhook, tiếp tục với [Kiểm thử Đơn vị Tự động](../../3-automated-unit-test/3.1-write-unit-tests/)
