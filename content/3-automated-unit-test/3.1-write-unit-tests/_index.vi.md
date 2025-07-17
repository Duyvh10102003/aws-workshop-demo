---
title: "Viết Unit Tests"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>3.1. </b>"
---

## Viết Unit Tests

### Tạo Dự án Kiểm thử
[Chèn ảnh: Tạo dự án kiểm thử mới trong VS Code]
1. Tạo Dự án Kiểm thử
   - Mở terminal trong thư mục giải pháp
   - Tạo dự án xUnit mới
   [Chèn ảnh: Lệnh terminal và kết quả]

2. Thêm Tham chiếu Dự án
   [Chèn ảnh: Thêm tham chiếu dự án trong VS Code]
   - Tham chiếu dự án chính
   - Xác minh tham chiếu đã thêm
   [Chèn ảnh: Xác nhận tham chiếu dự án]

### Viết Kiểm thử Cơ bản
[Chèn ảnh: VS Code với file kiểm thử đang mở]
1. Tạo Kiểm thử Calculator
   ```csharp
   // Ví dụ kiểm thử đơn giản
   public class CalculatorTests
   {
       [Fact]
       public void Add_TwoNumbers_ReturnsSum()
       {
           var calc = new Calculator();
           var result = calc.Add(2, 3);
           Assert.Equal(5, result);
       }
   }
   ```
   [Chèn ảnh: Mã kiểm thử với phần được đánh dấu]

### Tổ chức Kiểm thử
[Chèn ảnh: Cấu trúc dự án kiểm thử]
1. Cấu trúc Thư mục
   - Controllers/
   - Services/
   - Models/
   [Chèn ảnh: Thư mục kiểm thử có tổ chức]

2. Quy ước Đặt tên
   [Chèn ảnh: Ví dụ đặt tên kiểm thử]
   - TenLop_TenPhuongThuc_KetQuaMongDoi
   - Tên rõ ràng và mô tả

### Chạy Kiểm thử Cục bộ
[Chèn ảnh: Test Explorer trong VS Code]
1. Sử dụng Test Explorer
   - Mở Test Explorer
   - Chạy tất cả kiểm thử
   - Xem kết quả
   [Chèn ảnh: Hiển thị kết quả kiểm thử]

2. Sử dụng Command Line
   [Chèn ảnh: Terminal với lệnh kiểm thử]
   ```bash
   dotnet test
   ```

### Danh sách Xác minh
- [ ] Dự án kiểm thử đã tạo
- [ ] Tham chiếu dự án đã thêm
- [ ] Kiểm thử cơ bản đã viết
- [ ] Kiểm thử chạy thành công
- [ ] Kết quả hiển thị chính xác

### Hướng dẫn Xử lý Sự cố
[Chèn ảnh: Vấn đề kiểm thử phổ biến]
1. Vấn đề Tham chiếu Dự án
   - Kiểm tra đường dẫn dự án
   - Xác minh phiên bản framework
   - Xem xét dependencies

2. Vấn đề Phát hiện Kiểm thử
   - Kiểm tra thuộc tính kiểm thử
   - Xác minh lớp kiểm thử public
   - Xem xét quy ước đặt tên

3. Vấn đề Thực thi Kiểm thử
   - Kiểm tra lỗi runtime
   - Xác minh dependencies
   - Xem xét ngữ cảnh kiểm thử

### Thực hành Tốt nhất
[Chèn ảnh: Thực hành tốt nhất viết kiểm thử]
1. Cấu trúc Kiểm thử
   - Mẫu Arrange-Act-Assert
   - Trách nhiệm đơn lẻ
   - Khẳng định rõ ràng

2. Tổ chức Mã
   - Nhóm logic
   - Đặt tên nhất quán
   - Cô lập phù hợp

### Bước tiếp theo
Sau khi viết kiểm thử cơ bản, tiếp tục với [Thiết lập BuildSpec](../3.2-buildspec-setup/)
