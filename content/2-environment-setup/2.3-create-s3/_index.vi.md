---
title: "2.3 - Tạo S3 Bucket"
weight: 3
chapter: false
---

# 🪣 Tạo S3 Bucket

Trong phần này, bạn sẽ tạo một S3 bucket để lưu trữ báo cáo test từ AWS CodeBuild.

---

## 🔧 Các bước thực hiện

### 1️⃣ Truy cập Amazon S3

1. Đăng nhập vào AWS Console
2. Tìm và chọn dịch vụ **S3**

![Access S3](/images/2-environment-setup/2.3-create-s3/access-s3.jpg)

### 2️⃣ Tạo Bucket

1. Nhấn nút **Create bucket**
2. Nhập tên bucket: `dotnet-unit-test-report`
3. Giữ các cài đặt khác ở mặc định
4. Nhấn **Create bucket**

![Create Bucket](/images/2-environment-setup/2.3-create-s3/create-bucket.png)

![Create Bucket](/images/2-environment-setup/2.3-create-s3/create-bucket2.png)

### 3️⃣ Xác nhận

- Bucket mới sẽ xuất hiện trong danh sách
- Trạng thái bucket là "Created"

![Bucket Created](/images/2-environment-setup/2.3-create-s3/bucket-created.png)

---

## 📝 Ghi chú

- Bucket này sẽ được sử dụng để lưu báo cáo test từ CodeBuild
- Tên bucket phải là duy nhất trên toàn cầu
- Các cài đặt mặc định đã đủ cho mục đích của workshop
