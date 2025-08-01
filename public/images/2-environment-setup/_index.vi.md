---
title: "Thiết Lập Môi Trường"
date: 2025-07-04
weight: 2
chapter: false
pre: "<b>2. </b>"
---

## Tổng Quan Về Thiết Lập Môi Trường

Module này hướng dẫn bạn thiết lập môi trường cho kiểm thử tự động với AWS CodeBuild. Bạn có thể sử dụng website mẫu có sẵn hoặc triển khai website của riêng bạn để kiểm thử.

### Những Gì Bạn Sẽ Học

1. Tùy Chọn Thiết Lập Website
   - Tùy chọn A: Sử dụng website xem phim mẫu
   - Tùy chọn B: Triển khai website của riêng bạn lên GitHub

2. Cài Đặt Công Cụ Cần Thiết
   - Cài đặt và cấu hình AWS CLI
   - Thiết lập công cụ phát triển
   - Cài đặt SDK cần thiết

3. Thiết Lập Dự Án CodeBuild
   - Tạo dự án AWS CodeBuild
   - Cấu hình đặc tả build
   - Thiết lập vai trò và quyền IAM

### Điều Kiện Tiên Quyết

Trước khi bắt đầu module này, hãy đảm bảo bạn có:
- Tài khoản AWS với quyền thích hợp
- Tài khoản GitHub
- Kiến thức cơ bản về Git và GitHub
- Quyền truy cập quản trị vào máy phát triển của bạn

### Ước Tính Thời Gian
- Tổng thời gian Module: ~1 giờ
- Thời gian cho mỗi phần: 15-20 phút

### Cấu Trúc Module

1. [Thiết Lập Website](2.1-website-setup/)
   - Sử dụng website xem phim mẫu
   - HOẶC triển khai website của riêng bạn

2. [Cài Đặt Công Cụ Cần Thiết](2.2-install-tools/)
   - Thiết lập môi trường phát triển
   - Cài đặt công cụ AWS

3. [Tạo Dự Án CodeBuild](2.3-codebuild-project/)
   - Cấu hình AWS CodeBuild
   - Thiết lập pipeline build

### Kết Quả Mong Đợi

Khi kết thúc module này, bạn sẽ có:
- Một repository website hoạt động trên GitHub
- Tất cả công cụ phát triển cần thiết được cài đặt
- Một dự án AWS CodeBuild sẵn sàng cho kiểm thử tự động

Hãy bắt đầu với [Thiết Lập Website](2.1-website-setup/)!
