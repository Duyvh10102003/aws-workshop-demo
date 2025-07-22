---
title: "Cài Đặt Công Cụ Cần Thiết"
date: 2025-07-04
weight: 2
chapter: false
pre: "<b>2.2. </b>"
---

## Cài Đặt Công Cụ Cần Thiết

Để tiến hành kiểm thử tự động bằng AWS CodeBuild, bạn cần cài đặt và cấu hình một số công cụ.

### 1. Cài Đặt AWS CLI

#### Cho Windows:
1. Tải trình cài đặt AWS CLI MSI:
   - Truy cập: https://aws.amazon.com/cli/
   - Tải xuống bản cài đặt Windows x64

2. Chạy trình cài đặt:
   - Nhấp đúp vào file đã tải
   - Làm theo hướng dẫn cài đặt
   - Kiểm tra cài đặt bằng cách mở Command Prompt và chạy:
     ```bash
     aws --version
     ```

#### Cho Linux:
```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

#### Cho macOS:
```bash
brew install awscli
```

### 2. Cấu Hình AWS CLI

1. Lấy thông tin xác thực AWS:
   - Access Key ID
   - Secret Access Key
   - Vùng mặc định (ví dụ: us-east-1)

2. Chạy cấu hình:
   ```bash
   aws configure
   ```

3. Nhập thông tin xác thực khi được yêu cầu:
   ```
   AWS Access Key ID: [Access Key của bạn]
   AWS Secret Access Key: [Secret Key của bạn]
   Default region name: [Vùng của bạn]
   Default output format: json
   ```

### 3. Cài Đặt Git (nếu chưa có)

#### Cho Windows:
- Tải từ: https://git-scm.com/download/win
- Chạy trình cài đặt với tùy chọn mặc định

#### Cho Linux:
```bash
sudo apt-get update
sudo apt-get install git
```

#### Cho macOS:
```bash
brew install git
```

### 4. Visual Studio Code (Tùy chọn nhưng khuyến nghị)

1. Tải VS Code:
   - Truy cập: https://code.visualstudio.com/
   - Chọn phiên bản cho nền tảng của bạn

2. Cài đặt các tiện ích mở rộng được khuyến nghị:
   - AWS Toolkit
   - C# Dev Kit
   - Git Extension Pack

### Các Bước Xác Minh

1. Kiểm tra AWS CLI:
```bash
aws --version
```

2. Kiểm tra Git:
```bash
git --version
```

3. Kiểm tra cấu hình AWS:
```bash
aws sts get-caller-identity
```

### Xử Lý Sự Cố

1. Vấn đề với AWS CLI:
   - Đảm bảo thông tin xác thực AWS chính xác
   - Kiểm tra quyền của người dùng IAM
   - Xác minh vùng mặc định được cài đặt đúng

2. Vấn đề với Git:
   - Đảm bảo Git nằm trong PATH của hệ thống
   - Cấu hình Git với thông tin của bạn:
     ```bash
     git config --global user.name "Tên Của Bạn"
     git config --global user.email "email.cua.ban@example.com"
     ```

### Bước Tiếp Theo

Sau khi cài đặt và cấu hình tất cả công cụ cần thiết, tiếp tục với phần [Tạo S3 Bucket](../2.3-create-s3/)
