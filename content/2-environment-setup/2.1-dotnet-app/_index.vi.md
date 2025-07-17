---
title: "Thiết lập Ứng dụng .NET"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>2.1. </b>"
---

## Thiết lập Ứng dụng .NET

### Các bước Cài đặt
[Chèn ảnh: Trang tải .NET SDK]
1. Tải .NET 8 SDK
   - Truy cập https://dotnet.microsoft.com/download
   - Chọn .NET 8 SDK
   - Chọn hệ điều hành của bạn
   [Chèn ảnh: Tùy chọn tải xuống với nút được đánh dấu]

2. Cài đặt SDK
   [Chèn ảnh: Các bước trình hướng dẫn cài đặt]
   - Chạy trình cài đặt
   - Làm theo hướng dẫn
   - Chấp nhận tùy chọn mặc định
   - Đợi hoàn thành

3. Xác minh Cài đặt
   [Chèn ảnh: Command prompt với kiểm tra phiên bản]
   ```bash
   dotnet --version
   ```
   Kết quả mong đợi: 8.0.x

### Tạo Dự án Kiểm thử
[Chèn ảnh: VS Code tạo dự án mới]
1. Mở Terminal/Command Prompt
2. Di chuyển đến workspace của bạn
3. Tạo dự án MVC mới:
   ```bash
   dotnet new mvc -n TestAutomationDemo
   ```
   [Chèn ảnh: Kết quả tạo dự án]

### Cấu trúc Dự án
[Chèn ảnh: Cấu trúc dự án trong VS Code]
Dự án của bạn nên bao gồm:
- Controllers/
- Models/
- Views/
- wwwroot/
- Program.cs
- appsettings.json

### Danh sách Xác minh
- [ ] .NET SDK đã cài đặt thành công
- [ ] Dự án tạo không có lỗi
- [ ] Có thể build dự án (`dotnet build`)
- [ ] Có thể chạy dự án (`dotnet run`)
- [ ] Có thể truy cập trang chủ (https://localhost:5001)

### Hướng dẫn Xử lý Sự cố
[Chèn ảnh: Lỗi phổ biến và giải pháp]
1. Không tìm thấy SDK
   - Kiểm tra biến môi trường PATH
   - Cài đặt lại SDK nếu cần
   
2. Cổng đã được sử dụng
   - Kiểm tra ứng dụng đang chạy
   - Thay đổi cổng trong launchSettings.json

3. Lỗi Build
   - Xóa cache NuGet
   - Khôi phục gói
   - Kiểm tra phiên bản SDK

### Bước tiếp theo
Sau khi xác minh thiết lập .NET, tiếp tục với [Thiết lập GitHub Repository](../2.2-github-repo/)
