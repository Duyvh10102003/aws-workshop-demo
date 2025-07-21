---
title: "Thiết Lập Dự Án CodeBuild"
date: 2025-07-04
weight: 3
chapter: false
pre: "<b>2.3. </b>"
---

## Thiết Lập Dự Án AWS CodeBuild

Trong phần này, chúng ta sẽ tạo và cấu hình một dự án AWS CodeBuild để chạy các bài kiểm thử tự động.

### 1. Tạo IAM Role cho CodeBuild

1. Mở AWS Management Console
2. Điều hướng đến dịch vụ IAM
3. Tạo role mới:
   - Chọn AWS service làm trusted entity
   - Chọn CodeBuild làm use case
   - Thêm các chính sách được quản lý:
     - AWSCodeBuildAdminAccess
     - AmazonS3FullAccess (cho test artifacts)

### 2. Tạo Dự Án CodeBuild

1. Mở AWS CodeBuild console
2. Nhấp vào "Create build project"
3. Cấu hình các thiết lập dự án:

   **Cấu hình dự án**
   ```
   Tên dự án: website-automated-testing
   Mô tả: Kiểm thử tự động cho website sử dụng CodeBuild
   ```

   **Nguồn**
   ```
   Nhà cung cấp nguồn: GitHub
   Repository: Chọn repository của bạn
   Nhánh: main (hoặc nhánh bạn muốn)
   ```

   **Môi trường**
   ```
   Image môi trường: Managed image
   Hệ điều hành: Ubuntu
   Runtime: Standard
   Image: aws/codebuild/standard:7.0
   Loại môi trường: Linux
   Service role: Sử dụng role đã tạo ở bước 1
   ```

   **Buildspec**
   ```
   Build specifications: Sử dụng file buildspec
   Tên buildspec: buildspec.yml
   ```

   **Artifacts**
   ```
   Loại: Không có artifacts
   ```

### 3. Tạo File buildspec.yml Cơ Bản

Trong thư mục gốc của repository, tạo file `buildspec.yml`:

```yaml
version: 0.2

phases:
  install:
    runtime-versions:
      dotnet: 8.0
    commands:
      - echo Đang cài đặt dependencies...
      
  pre_build:
    commands:
      - echo Giai đoạn pre-build...
      
  build:
    commands:
      - echo Bắt đầu build...
      
  post_build:
    commands:
      - echo Hoàn thành build...

reports:
  test-reports:
    files:
      - '**/*'
    base-directory: 'testresults'
    file-format: VisualStudioTrx
```

### 4. Kiểm Tra Build

1. Lưu tất cả cấu hình
2. Nhấp "Start build" trong console CodeBuild
3. Theo dõi tiến trình build
4. Kiểm tra logs build để phát hiện vấn đề

### Lưu Ý Quan Trọng

1. **Truy Cập Repository**:
   - Với repository công khai: Không cần thiết lập thêm
   - Với repository riêng tư: Cần cấu hình xác thực GitHub

2. **Logs Build**:
   - Có sẵn trong CloudWatch Logs
   - Được lưu giữ trong 30 ngày theo mặc định

3. **Chi Phí**:
   - CodeBuild tính phí theo phút build
   - Free tier bao gồm 100 phút build mỗi tháng

### Xử Lý Các Vấn Đề Thường Gặp

1. **Lỗi Build**:
   - Kiểm tra quyền của IAM role
   - Xác minh cú pháp buildspec.yml
   - Đảm bảo tất cả file cần thiết tồn tại trong repository

2. **Vấn Đề Kết Nối GitHub**:
   - Kiểm tra trạng thái kết nối GitHub
   - Kiểm tra quyền repository
   - Xác nhận cấu hình webhook

### Bước Tiếp Theo

Giờ đây môi trường của bạn đã được thiết lập, bạn có thể tiếp tục với module tiếp theo để bắt đầu triển khai các bài kiểm thử tự động.
