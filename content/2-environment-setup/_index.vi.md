---
title: "Thiết lập Môi trường"
date: 2025-07-04
weight: 2
chapter: false
pre: "<b>2. </b>"
---

## Tổng quan về Thiết lập Môi trường

Module này hướng dẫn bạn thiết lập môi trường phát triển và kiểm thử cho việc tự động hóa kiểm thử với AWS CodeBuild. Chúng ta sẽ thiết lập tất cả các thành phần cần thiết để tạo một pipeline tích hợp liên tục mạnh mẽ.

### Những gì Bạn sẽ Học

1. Thiết lập Ứng dụng .NET
   - Tạo dự án .NET 8 MVC mới
   - Cấu hình cấu trúc ứng dụng cơ bản
   - Thêm các dependency kiểm thử ban đầu

2. Cấu hình GitHub Repository
   - Tạo và khởi tạo repository
   - Thiết lập bảo vệ nhánh
   - Cấu hình quy trình phát triển

3. Cài đặt Công cụ Cần thiết
   - Cài đặt và cấu hình AWS CLI
   - Thiết lập công cụ phát triển
   - Cài đặt SDK cần thiết

4. Thiết lập Dự án CodeBuild
   - Tạo dự án AWS CodeBuild
   - Cấu hình đặc tả build
   - Thiết lập vai trò và quyền IAM

5. Tích hợp Webhook
   - Cấu hình webhook GitHub
   - Kiểm tra kích hoạt tự động
   - Xác minh pipeline build

### Yêu cầu Tiên quyết

Trước khi bắt đầu module này, đảm bảo bạn có:
- Tài khoản AWS với quyền thích hợp
- Kiến thức cơ bản về Git và GitHub
- Hiểu biết về phát triển .NET
- Quyền truy cập quản trị vào máy phát triển của bạn

### Ước tính Thời gian
- Tổng thời gian Module: ~2 giờ
- Thời gian mỗi Phần: 20-30 phút

### Cấu trúc Module

1. [Thiết lập Ứng dụng .NET](2.1-dotnet-app/)
   - Thiết lập ứng dụng cơ bản
   - Cấu hình ban đầu

2. [Thiết lập GitHub Repository](2.2-github-repo/)
   - Tạo repository
   - Cấu hình nhánh

3. [Cài đặt Công cụ Cần thiết](2.3-install-tools/)
   - Thiết lập môi trường phát triển
   - Cài đặt công cụ AWS

4. [Tạo Dự án CodeBuild](2.4-codebuild-project/)
   - Cấu hình AWS CodeBuild
   - Thiết lập pipeline build

5. [Xác minh Webhook](2.5-webhook-verify/)
   - Kiểm tra tích hợp
   - Xác minh tự động hóa

### Kết quả Mong đợi

Đến cuối module này, bạn sẽ có:
- Một ứng dụng .NET hoạt động
- Một GitHub repository đã được cấu hình
- Tất cả công cụ phát triển cần thiết đã được cài đặt
- Một dự án AWS CodeBuild hoạt động
- Kích hoạt build tự động thông qua webhook

Hãy bắt đầu với [Thiết lập Ứng dụng .NET](2.1-dotnet-app/)!
