---
title: "Thiết lập CodeBuild để chạy Unit Test"
date: 2025-07-04
weight: 3
chapter: false
pre: "<b>3.3. </b>"
---

Trong phần này, bạn sẽ tạo một project CodeBuild để chạy tự động unit test từ mã nguồn trong GitHub, sử dụng file `buildspec.yml` đã cấu hình ở bước trước.

---

## 🎯 Mục tiêu

- Tạo project trong AWS CodeBuild
- Kết nối GitHub với AWS
- Cấu hình môi trường chạy build
- Chạy `buildspec.yml` đã thiết lập từ repo
- (Tuỳ chọn) Lưu báo cáo test lên Amazon S3

---

## 🔧 Các bước thực hiện

### 1️⃣ Truy cập AWS CodeBuild

- Mở trang: [https://console.aws.amazon.com/codebuild/home](https://console.aws.amazon.com/codebuild/home)
- Nhấn **Create build project**

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/CreateCodeBuilder.png)

---

### 2️⃣ Nhập thông tin Project

- **Project name**: `ci-dotnet-unittest`
- **Description**: `Chạy unit test và sinh báo cáo HTML`

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/CreateProject.png)

---

### 3️⃣ Cấu hình nguồn (Source)

1. Trong phần **Source**, chọn **Source provider** là **GitHub (Version 2)** và chọn **Manage account credentials** nếu bạn chưa kết nối GitHub.

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/Source.png)

2. Nhấn **create a new GitHub connection** để bắt đầu tạo kết nối

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github1.png)

3. Một cửa sổ mới sẽ mở ra. Nhập tên cho connection:

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github2.png)

4. Chọn **Install a new app** để kết nối tới GitHub của bạn

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github3.png)

5. Nhập mật khẩu GitHub để kết nối

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github4.png)

6. Sau khi kết nối thành công, bạn sẽ thấy thông báo xác nhận

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github5.png)

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github6.png)

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github7.png)

7. Quay lại trang **Manage default source credential**, chọn connection vừa tạo

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github8.png)

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github9.png)

8. Quay lại trang CodeBuild, chọn repository vừa kết nối và chọn branch chính của dự án (thường là `main` hoặc `master`)

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github10.png)

9. Trong phần **Primary source webhook events**, chọn ✅ Tick vào "Rebuild every time a code change is pushed to this repository"

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/webhook.png)

---

### 4️⃣ Thiết lập môi trường build

- **Provisioning model**: `On-demand`
- **Environment image**: `Managed image`
- **Compute**: `EC2`
- **Running mode**: `Container`
- **Operating System**: `Amazon Linux`
- **Runtime**: `Standard`
- **Image**: `aws/codebuild/amazonlinux-x86_64-standard:5.0` 

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/environment.png)

---

### 5️⃣ Buildspec file

- **Buildspec**: chọn `Use a buildspec file`
- Đảm bảo repo của bạn có file `buildspec.yml` ở thư mục gốc

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/buildspec.png)

---

### 6️⃣ (Tuỳ chọn) Artifact để lưu báo cáo

- Nếu bạn muốn lưu báo cáo test HTML:
  - **Artifacts type**: `Amazon S3`
  - **S3 bucket**: chọn bucket đã tạo trước

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/S3.png)

---

### 7️⃣ Tạo project

- Nhấn **Create build project**
- Sau khi tạo xong:
  - Có thể chọn **Start build** để chạy thử
  - Hoặc push code lên GitHub để webhook tự động chạy
![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/Cloudwatch.png)

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/doneCreate.png)

---

## 🧠 Mẹo thêm

- Nếu repo chưa có `buildspec.yml`, bạn có thể dùng tuỳ chọn "Insert build commands" để viết trực tiếp, nhưng không khuyến khích.
- Sau khi tạo project, AWS sẽ tự chạy test mỗi lần bạn nhấn "Start build" hoặc khi có push (nếu bật webhook).
- Với GitHub version 2, bạn có thể chọn repo từ dropdown. Nếu dùng PAT thì cần dán token thủ công.


