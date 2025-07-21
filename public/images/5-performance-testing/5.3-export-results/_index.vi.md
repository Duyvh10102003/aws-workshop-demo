---
title: "Xuất Kết quả"
date: 2025-07-04
weight: 3
chapter: false
pre: "<b>5.3. </b>"
---

## Xuất Kết quả Kiểm thử Hiệu năng

### Cấu hình Xuất Kết quả
[Chèn ảnh: Cấu hình xuất kết quả]
1. Thiết lập Định dạng Xuất
   ```javascript
   // Cấu hình xuất k6
   export const options = {
     ext: {
       loadimpact: {
         projectID: 123456,
       },
     },
     outputFields: {
       metrics: ['http_req_duration', 'http_reqs', 'vus'],
       trend: ['p95', 'avg', 'med', 'min', 'max'],
     },
   };
   ```
   [Chèn ảnh: Cấu hình xuất]

2. Cấu hình Vị trí Lưu trữ
   [Chèn ảnh: Thiết lập lưu trữ]
   - Cấu hình bucket S3
   - Tổ chức file
   - Chính sách lưu giữ

### Triển khai Xử lý Dữ liệu
[Chèn ảnh: Thiết lập xử lý dữ liệu]
1. Tạo Script Xử lý
   - Phân tích kết quả kiểm thử
   - Tính toán chỉ số
   - Tạo tổng hợp
   [Chèn ảnh: Triển khai xử lý]

2. Thiết lập Pipeline Dữ liệu
   [Chèn ảnh: Pipeline dữ liệu]
   - Luồng dữ liệu
   - Bước chuyển đổi
   - Định dạng đầu ra

### Tạo Báo cáo
[Chèn ảnh: Tạo báo cáo]
1. Cấu hình Mẫu
   - Chỉ số hiệu năng
   - Phân tích xu hướng
   - Góc nhìn so sánh
   [Chèn ảnh: Mẫu báo cáo]

2. Thiết lập Phân phối
   [Chèn ảnh: Phân phối báo cáo]
   - Gửi email
   - Cập nhật bảng điều khiển
   - Hệ thống thông báo

### Danh sách Xác minh
- [ ] Xuất đã cấu hình
- [ ] Xử lý hoạt động
- [ ] Báo cáo đang tạo
- [ ] Phân phối hoạt động
- [ ] Lưu trữ có tổ chức

### Hướng dẫn Xử lý Sự cố
[Chèn ảnh: Vấn đề xuất phổ biến]
1. Vấn đề Xuất
   - Lỗi định dạng
   - Vấn đề lưu trữ
   - Vấn đề quyền

2. Vấn đề Xử lý
   - Hỏng dữ liệu
   - Lỗi tính toán
   - Giới hạn tài nguyên

3. Vấn đề Báo cáo
   - Lỗi mẫu
   - Lỗi phân phối
   - Vấn đề truy cập

### Thực hành Tốt nhất
[Chèn ảnh: Thực hành tốt nhất xuất]
1. Quản lý Dữ liệu
   - Tổ chức rõ ràng
   - Dọn dẹp thường xuyên
   - Sao lưu phù hợp

2. Thiết kế Báo cáo
   - Trình bày rõ ràng
   - Chỉ số chính
   - Thông tin có thể hành động

### Bước tiếp theo
Sau khi thiết lập xuất kết quả, tiếp tục với [Phân tích Hiệu năng](../5.4-analyze-performance/)
