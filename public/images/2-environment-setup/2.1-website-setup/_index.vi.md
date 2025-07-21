---
title: "Thiết lập Website"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>2.1. </b>"
---

## Các Tùy Chọn Thiết Lập Website

Bạn có hai lựa chọn để thiết lập website cho workshop này:

### Tùy Chọn A: Sử Dụng Website Xem Phim Mẫu

1. Fork repository website xem phim mẫu:
   - Truy cập: https://github.com/Duyvh10102003/WebsiteXemPhim
   - Nhấp vào nút "Fork" ở góc trên bên phải
   - Chọn tài khoản GitHub của bạn làm điểm đến

2. Clone repository đã fork:
   ```bash
   git clone https://github.com/[TÊN-NGƯỜI-DÙNG]/WebsiteXemPhim.git
   cd WebsiteXemPhim
   ```

3. Chuyển sang nhánh HoangDuy:
   ```bash
   git checkout HoangDuy
   ```

### Tùy Chọn B: Sử Dụng Website Của Riêng Bạn

Nếu bạn muốn sử dụng website của riêng mình, hãy làm theo các bước sau:

1. Tạo repository GitHub mới:
   - Truy cập https://github.com/new
   - Đặt tên cho repository
   - Chọn chế độ hiển thị công khai hoặc riêng tư
   - Khởi tạo với README nếu muốn

2. Đẩy code website của bạn lên:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/[TÊN-NGƯỜI-DÙNG]/[TÊN-REPO].git
   git push -u origin main
   ```

### Lưu Ý Quan Trọng

- Đảm bảo code website của bạn nằm ở thư mục gốc của repository
- Repository phải có thể truy cập được bởi AWS CodeBuild
- Nếu sử dụng repository riêng tư, sẽ cần thêm cấu hình cho AWS CodeBuild

### Bước Tiếp Theo

Sau khi hoàn thành một trong hai tùy chọn trên, hãy tiếp tục với phần [Cài Đặt Công Cụ Cần Thiết](../2.2-install-tools/)
