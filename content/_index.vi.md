---
title: "Automated Testing with AWS CodeBuild"
date: 2025-07-12
weight: 1
chapter: false
---

# Workshop: Kiểm thử tự động với AWS CodeBuild và thực thi song song

### Tổng quan

Trong workshop này, bạn sẽ học cách xây dựng một hệ thống kiểm thử tự động hiện đại cho ứng dụng web viết bằng .NET 8 MVC, sử dụng các dịch vụ AWS như **CodeBuild, CloudWatch, và CodeQL**.

Thông qua từng phần thực hành, bạn sẽ:
- Thiết lập pipeline CI kiểm thử tự động khi push code lên GitHub
- Thực thi kiểm thử song song (parallel execution) để tối ưu thời gian
- Tích hợp kiểm thử hiệu năng và bảo mật (CodeQL)
- Theo dõi logs, phân tích chi phí, và dọn dẹp tài nguyên sau workshop
- Dọn dẹp tài nguyên AWS sau khi thử nghiệm

![](/images/aws-test-arch.png)

### Nội dung workshop

1. [Giới thiệu & mục tiêu](1-introduction/)
2. [Chuẩn bị môi trường](2-environment-setup/)
3. [Thiết lập kiểm thử tự động](3-automated-unit-test/)
4. [Thực thi song song & tổng hợp kết quả](4-parallel-execution/)
5. [Kiểm thử hiệu năng](5-performance-testing/)
6. [Kiểm thử bảo mật với CodeQL](6-security-testing/)
7. [Theo dõi, báo cáo & tối ưu chi phí](7-monitoring-cost/)
8. [Dọn dẹp tài nguyên](8-clean-up/)
