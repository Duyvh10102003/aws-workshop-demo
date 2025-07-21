---
title: "Viết Kiểm thử Hiệu năng"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>5.1. </b>"
---

## Viết Kiểm thử Hiệu năng

### Thiết lập Công cụ k6
[Chèn ảnh: Cài đặt k6]
1. Cài đặt k6
   - Hướng dẫn tải xuống
   - Các bước cài đặt
   - Quy trình xác minh
   [Chèn ảnh: Xác minh cài đặt]

2. Cấu hình Môi trường
   [Chèn ảnh: Cấu hình k6]
   - Thiết lập cơ bản
   - Biến môi trường
   - Cấu trúc kiểm thử

### Tạo Kiểm thử Tải Cơ bản
[Chèn ảnh: Tạo kiểm thử tải cơ bản]
1. Viết Script Kiểm thử Tải
   ```javascript
   import http from 'k6/http';
   import { check, sleep } from 'k6';

   export const options = {
     stages: [
       { duration: '1m', target: 20 },
       { duration: '2m', target: 20 },
       { duration: '1m', target: 0 },
     ],
   };

   export default function () {
     const response = http.get('http://test.api/endpoint');
     check(response, {
       'trạng thái là 200': (r) => r.status === 200,
     });
     sleep(1);
   }
   ```
   [Chèn ảnh: Thực thi script]

### Triển khai Kịch bản Kiểm thử
[Chèn ảnh: Triển khai kịch bản kiểm thử]
1. Tạo Ca Kiểm thử
   - Kiểm thử tải
   - Kiểm thử áp lực
   - Kiểm thử đột biến
   [Chèn ảnh: Các loại kiểm thử]

2. Cấu hình Chỉ số
   [Chèn ảnh: Cấu hình chỉ số]
   - Thời gian phản hồi
   - Tỷ lệ lỗi
   - Thông lượng

### Danh sách Xác minh
- [ ] k6 đã cài đặt đúng
- [ ] Kiểm thử cơ bản đang chạy
- [ ] Chỉ số đang thu thập
- [ ] Kịch bản đã triển khai
- [ ] Kết quả đang ghi lại

### Hướng dẫn Xử lý Sự cố
[Chèn ảnh: Vấn đề k6 phổ biến]
1. Vấn đề Cài đặt
   - Vấn đề đường dẫn
   - Dependencies
   - Xung đột phiên bản

2. Vấn đề Script
   - Lỗi cú pháp
   - Vấn đề logic
   - Giới hạn tài nguyên

3. Vấn đề Thực thi
   - Vấn đề kết nối
   - Hạn chế tài nguyên
   - Lỗi thời gian chờ

### Thực hành Tốt nhất
[Chèn ảnh: Thực hành tốt nhất kiểm thử hiệu năng]
1. Thiết kế Kiểm thử
   - Mục tiêu rõ ràng
   - Kịch bản thực tế
   - Chỉ số phù hợp

2. Tổ chức Script
   - Mã module hóa
   - Hàm có thể tái sử dụng
   - Tài liệu rõ ràng

### Bước tiếp theo
Sau khi viết kiểm thử hiệu năng, tiếp tục với [Tích hợp CI/CD](../5.2-integrate-into-ci/)
