---
title: "Đẩy và Kích hoạt"
date: 2025-07-04
weight: 3
chapter: false
pre: "<b>3.3. </b>"
---

## Đẩy Thay đổi và Kích hoạt Kiểm thử

### Chuẩn bị Thay đổi
[Chèn ảnh: VS Code với các thay đổi]
1. Xem xét Thay đổi
   - Kiểm tra file đã sửa đổi
   - Xác minh file kiểm thử
   - Xem xét buildspec
   [Chèn ảnh: Thay đổi Git trong VS Code]

2. Stage Thay đổi
   [Chèn ảnh: Stage thay đổi]
   ```bash
   git add .
   git status
   ```

### Commit và Push
[Chèn ảnh: Hộp thoại commit]
1. Tạo Commit
   ```bash
   git commit -m "feat: thêm kiểm thử tự động"
   ```
   [Chèn ảnh: Xác nhận commit]

2. Đẩy lên GitHub
   ```bash
   git push origin main
   ```
   [Chèn ảnh: Push thành công]

### Theo dõi Build
[Chèn ảnh: Bảng điều khiển CodeBuild]
1. Theo dõi Tiến trình Build
   - Mở bảng điều khiển CodeBuild
   - Tìm build mới nhất
   - Theo dõi các giai đoạn
   [Chèn ảnh: Tiến trình build]

2. Kiểm tra Log Build
   [Chèn ảnh: Log build]
   - Xem log thời gian thực
   - Kiểm tra thực thi kiểm thử
   - Theo dõi kết quả

### Danh sách Xác minh
- [ ] Thay đổi đã đẩy thành công
- [ ] Build được kích hoạt tự động
- [ ] Kiểm thử thực thi đúng
- [ ] Kết quả được báo cáo
- [ ] Log có sẵn

### Hướng dẫn Xử lý Sự cố
[Chèn ảnh: Vấn đề thường gặp]
1. Vấn đề Push
   - Kiểm tra thông tin xác thực
   - Xác minh remote
   - Xem xét quyền

2. Vấn đề Kích hoạt
   - Kiểm tra webhook
   - Xác minh cấu hình build
   - Xem xét vai trò IAM

3. Lỗi Build
   - Kiểm tra môi trường
   - Xem xét dependencies
   - Xác minh thiết lập kiểm thử

### Thực hành Tốt nhất
[Chèn ảnh: Thực hành tốt nhất]
1. Quản lý Mã
   - Commit thường xuyên
   - Thông điệp rõ ràng
   - Nhánh tính năng

2. Giám sát Build
   - Theo dõi tiến trình
   - Kiểm tra log
   - Xác minh kết quả

### Bước tiếp theo
Sau khi xác nhận kích hoạt thành công, tiếp tục với [Xem Kết quả](../3.4-view-results/)
