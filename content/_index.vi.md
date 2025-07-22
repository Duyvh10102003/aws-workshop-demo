---
title: "Workshop Automated Testing Framework"
date: 2025-07-04
---

# 🚀 Xây dựng Framework Kiểm thử Tự động

{{% notice note %}}
Workshop này sẽ giúp bạn xây dựng một hệ thống kiểm thử tự động hoàn chỉnh cho website xem phim, sử dụng .NET và các dịch vụ AWS.
{{% /notice %}}

## 🎯 Bạn sẽ học được gì?

- Thiết lập pipeline CI/CD với AWS CodeBuild
- Viết và chạy unit test tự động
- Tối ưu hiệu năng với parallel testing
- Giám sát và nhận cảnh báo qua email
- Quét lỗi bảo mật tự động với CodeQL

## 📚 Nội dung Workshop

{{% children style="h3" depth="2" description="true" %}}

1. [**Giới thiệu**](1-introduction/) - Tổng quan về testing framework
2. [**Chuẩn bị môi trường**](2-environment-setup/) - Setup AWS và tools cần thiết
3. [**Unit Testing**](3-automated-unit-test/) - Viết test và cấu hình CodeBuild
4. [**Parallel Execution**](4-parallel-execution/) - Chạy test song song
5. [**Monitoring & Alerts**](5-monitoring/) - Theo dõi và cảnh báo
6. [**Security Testing**](6-security-testing/) - Quét bảo mật với CodeQL
7. [**Clean Up**](7-cleanup/) - Dọn dẹp tài nguyên

## ⚡ Quick Start

```bash
# Clone repository
git clone https://github.com/username/automated-testing-workshop

# Di chuyển vào thư mục
cd automated-testing-workshop

# Cài đặt dependencies
dotnet restore
```

## 🎓 Yêu cầu

- Kiến thức cơ bản về C# và .NET
- Tài khoản AWS (Free tier)
- Tài khoản GitHub
- Visual Studio Code hoặc Visual Studio

{{% notice tip %}}
Workshop này được thiết kế để hoàn thành trong 2-3 giờ. Bạn có thể chia nhỏ thành nhiều phiên học.
{{% /notice %}}
