---
title: "Gửi cảnh báo khi test thất bại"
date: 2025-07-04
weight: 5
chapter: false
pre: "<b>5. </b>"
---

# ⚡️ Gửi cảnh báo khi test thất bại bằng SNS và CloudWatch

Trong phần này, bạn sẽ học cách thiết lập hệ thống cảnh báo tự động khi có test thất bại, sử dụng Amazon CloudWatch để theo dõi và Amazon SNS để gửi thông báo.

## 🎯 Mục tiêu

- Tạo thông báo tự động (email, SMS...) khi một bản build thất bại
- Dùng Amazon CloudWatch để theo dõi trạng thái build
- Dùng Amazon SNS (Simple Notification Service) để gửi cảnh báo
- Giúp người quản lý/dev biết ngay khi có lỗi test xảy ra

## 🧱 Các bước thực hiện

| Bước | Mô tả ngắn |
|------|------------|
| 5.1 | Tạo SNS topic & đăng ký email nhận thông báo |
| 5.2 | Tạo CloudWatch Rule để bắt lỗi từ CodeBuild |
| 5.3 | Kết nối Rule → SNS topic để gửi cảnh báo |
| 5.4 | Test thử bằng build lỗi và xác nhận nhận được email |

## 🌐 Kiến trúc tổng quan

1. CodeBuild thực thi các bài test
2. CloudWatch theo dõi trạng thái của build
3. Khi phát hiện build thất bại, CloudWatch Rule được kích hoạt
4. Rule gửi thông báo tới SNS Topic
5. SNS gửi email tới các địa chỉ đã đăng ký

{{% children /%}}
