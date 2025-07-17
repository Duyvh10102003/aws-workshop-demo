---
title: "Cấu hình Cài đặt"
date: 2025-07-04
weight: 4
chapter: false
pre: "<b>6.4. </b>"
---

## Cấu hình Cài đặt Bảo mật

### Cấu hình Cài đặt CodeQL
[Chèn ảnh: Cấu hình CodeQL]
1. Cập nhật Cấu hình Phân tích
   ```yaml
   name: "Cấu hình CodeQL"
   
   queries:
     - uses: security-extended
     - uses: security-and-quality
   
   paths-ignore:
     - '**/test/**'
     - '**/generated/**'
   ```
   [Chèn ảnh: File cấu hình]

2. Thiết lập Bộ Truy vấn
   [Chèn ảnh: Thiết lập bộ truy vấn]
   - Chọn loại truy vấn
   - Cấu hình mức độ nghiêm trọng
   - Đặt phạm vi phân tích

### Cấu hình Cài đặt Cảnh báo
[Chèn ảnh: Cấu hình cảnh báo]
1. Đặt Quy tắc Cảnh báo
   - Ngưỡng mức độ nghiêm trọng
   - Quy tắc thông báo
   - Hành động phản hồi
   [Chèn ảnh: Quy tắc cảnh báo]

2. Cấu hình Thông báo
   [Chèn ảnh: Thiết lập thông báo]
   - Thông báo email
   - Cảnh báo tích hợp
   - Thông báo nhóm

### Quản lý Kiểm soát Bảo mật
[Chèn ảnh: Kiểm soát bảo mật]
1. Kiểm soát Truy cập
   - Quyền repository
   - Truy cập phân tích
   - Truy cập báo cáo
   [Chèn ảnh: Cài đặt truy cập]

2. Cấu hình Chính sách
   [Chèn ảnh: Thiết lập chính sách]
   - Chính sách bảo mật
   - Quy tắc thực thi
   - Cài đặt tuân thủ

### Danh sách Xác minh
- [ ] CodeQL đã cấu hình
- [ ] Cảnh báo đã thiết lập
- [ ] Thông báo hoạt động
- [ ] Kiểm soát truy cập đã xác minh
- [ ] Chính sách đã triển khai

### Hướng dẫn Xử lý Sự cố
[Chèn ảnh: Vấn đề cấu hình phổ biến]
1. Vấn đề Cấu hình
   - Lỗi cú pháp
   - Vấn đề quyền
   - Lỗi tích hợp

2. Vấn đề Cảnh báo
   - Thiếu thông báo
   - Cảnh báo sai
   - Quá tải cảnh báo

3. Vấn đề Truy cập
   - Từ chối quyền
   - Lỗi xác thực
   - Vấn đề tích hợp

### Thực hành Tốt nhất
[Chèn ảnh: Thực hành tốt nhất cấu hình]
1. Cài đặt Bảo mật
   - Xem xét thường xuyên
   - Tài liệu rõ ràng
   - Giao tiếp nhóm

2. Quản lý Cảnh báo
   - Mức độ ưu tiên
   - Quy trình phản hồi
   - Bảo trì thường xuyên

### Bước tiếp theo
Sau khi cấu hình cài đặt bảo mật, tiếp tục với [Giám sát Chi phí](../../7-monitoring-cost/7.1-cloudwatch-logs/)
