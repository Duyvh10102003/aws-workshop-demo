---
title: "Sửa Lỗ hổng"
date: 2025-07-04
weight: 3
chapter: false
pre: "<b>6.3. </b>"
---

## Sửa Lỗ hổng Bảo mật

### Chuẩn bị Môi trường Sửa lỗi
[Chèn ảnh: Thiết lập môi trường sửa lỗi]
1. Tạo Nhánh Sửa lỗi
   ```bash
   git checkout -b security-fix/issue-123
   ```
   [Chèn ảnh: Tạo nhánh]

2. Thiết lập Môi trường Phát triển
   [Chèn ảnh: Thiết lập phát triển]
   - Cấu hình IDE
   - Cài đặt công cụ bảo mật
   - Thiết lập môi trường kiểm thử

### Triển khai Sửa lỗi Bảo mật
[Chèn ảnh: Triển khai sửa lỗi]
1. Sửa Lỗ hổng Phổ biến
   ```csharp
   // Trước: Lỗ hổng SQL Injection
   var query = $"SELECT * FROM Users WHERE Id = {userId}";

   // Sau: Truy vấn có tham số
   var query = "SELECT * FROM Users WHERE Id = @UserId";
   command.Parameters.AddWithValue("@UserId", userId);
   ```
   [Chèn ảnh: Thay đổi mã]

2. Áp dụng Thực hành Bảo mật Tốt nhất
   [Chèn ảnh: Thực hành bảo mật]
   - Xác thực đầu vào
   - Mã hóa đầu ra
   - Cấu hình an toàn
   - Xử lý lỗi

### Kiểm thử Sửa lỗi Bảo mật
[Chèn ảnh: Kiểm thử bảo mật]
1. Chạy Kiểm thử Bảo mật
   - Kiểm thử đơn vị
   - Kiểm thử tích hợp
   - Quét bảo mật
   [Chèn ảnh: Thực thi kiểm thử]

2. Xác minh Sửa lỗi
   [Chèn ảnh: Xác minh sửa lỗi]
   - Kiểm tra kết quả CodeQL
   - Chạy kiểm thử thâm nhập
   - Xác thực kiểm soát bảo mật

### Gửi và Xem xét Thay đổi
[Chèn ảnh: Gửi thay đổi]
1. Tạo Pull Request
   - Mô tả chi tiết
   - Tác động bảo mật
   - Kết quả kiểm thử
   [Chèn ảnh: Tạo PR]

### Danh sách Xác minh
- [ ] Nhánh sửa lỗi đã tạo
- [ ] Sửa lỗi bảo mật đã triển khai
- [ ] Kiểm thử đã pass
- [ ] CodeQL sạch
- [ ] PR đã gửi

### Hướng dẫn Xử lý Sự cố
[Chèn ảnh: Vấn đề sửa lỗi phổ biến]
1. Vấn đề Triển khai
   - Xung đột mã
   - Lỗi kiểm thử
   - Vấn đề tích hợp

2. Quan ngại Bảo mật
   - Sửa lỗi không hoàn chỉnh
   - Lỗ hổng mới
   - Tác dụng phụ

3. Vấn đề Xem xét
   - Thiếu tài liệu
   - Thiếu kiểm thử
   - Thay đổi không rõ ràng

### Thực hành Tốt nhất
[Chèn ảnh: Thực hành tốt nhất sửa lỗi bảo mật]
1. Triển khai Sửa lỗi
   - Giải pháp hoàn chỉnh
   - Kiểm thử kỹ lưỡng
   - Tài liệu rõ ràng

2. Xem xét Mã
   - Tập trung bảo mật
   - Kiểm thử toàn diện
   - Phòng ngừa tương lai

### Bước tiếp theo
Sau khi sửa lỗ hổng, tiếp tục với [Cấu hình Cài đặt](../6.4-disable-if-needed/)
