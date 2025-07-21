---
title: "Framework Testing Tự Động"
date: 2025-07-04
weight: 3
chapter: false
pre: "<b>3. </b>"
---

Trong module này, chúng ta sẽ xây dựng một framework testing tự động cho website xem phim bằng cách sử dụng AWS CodeBuild và các công cụ testing hiện đại.

## 🎯 Mục tiêu

- Thiết lập môi trường testing tự động với AWS CodeBuild
- Viết và chạy unit test cho các component
- Tạo báo cáo test chi tiết và dễ đọc
- Tự động hóa quy trình testing khi có code mới

## 📋 Nội dung chính

1. [Viết Unit Test Đầu Tiên](3.1-codebuild-setup/)
   - Tạo test file đơn giản
   - Cấu trúc test cơ bản
   - Giả lập test delay

2. [Cấu Hình Buildspec](3.2-buildspec-setup/)
   - Tạo file buildspec.yml
   - Cài đặt công cụ báo cáo
   - Cấu hình output artifacts

3. [Thiết Lập CodeBuild](3.3-codebuild-project/)
   - Tạo project CodeBuild
   - Kết nối với GitHub
   - Cấu hình môi trường build

4. [Kiểm Tra Kết Quả](3.4-verify-results/)
   - Chạy và xem kết quả build
   - Phân tích báo cáo test
   - Xử lý lỗi (nếu có)

## ⚙️ Kiến thức cần có

- Hiểu biết cơ bản về testing trong .NET
- Đã cài đặt và cấu hình AWS CLI
- Có tài khoản GitHub với repository

## ⏱ Thời gian ước tính

- Tổng thời gian: ~2 giờ
- Mỗi phần: 25-30 phút

## 📌 Kết quả mong đợi

Sau khi hoàn thành module này, bạn sẽ có:

1. **Framework Testing Hoàn Chỉnh**
   - Unit test tự động chạy
   - Báo cáo test chi tiết
   - Tích hợp với GitHub

2. **Quy Trình CI/CD**
   - Tự động test khi push code
   - Lưu trữ kết quả test
   - Thông báo khi có lỗi

3. **Tài Liệu & Báo Cáo**
   - HTML test report
   - Log build chi tiết
   - Thống kê test coverage

## 🛠 Công cụ sử dụng

- **AWS CodeBuild**: Dịch vụ CI/CD tự động
- **xUnit**: Framework testing cho .NET
- **ReportGenerator**: Tạo báo cáo HTML
- **GitHub**: Quản lý source code

## 💡 Mẹo

- Đọc kỹ phần cấu hình buildspec.yml
- Test local trước khi push
- Kiểm tra log khi có lỗi
- Tổ chức test theo cấu trúc rõ ràng

## 🔍 Xử lý sự cố

- Kiểm tra quyền truy cập AWS
- Verify cấu hình GitHub
- Xem log build chi tiết
- Chạy test local để debug

{{% notice tip %}}
Hãy đảm bảo hoàn thành từng bước trước khi chuyển sang bước tiếp theo
{{% /notice %}}
