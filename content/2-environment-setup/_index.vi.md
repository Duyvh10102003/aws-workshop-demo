---
title: "Chuẩn bị Môi trường"
date: 2025-07-11
weight: 2
chapter : false
pre : " <b> 2. </b> "
---

Trong phần này, bạn sẽ thiết lập nền tảng ban đầu cần thiết để bắt đầu quy trình kiểm thử tự động với AWS. Đây là bước quan trọng nhằm đảm bảo mọi công cụ, mã nguồn, và kết nối đều sẵn sàng trước khi bước vào các giai đoạn kiểm thử phức tạp hơn.

## ✅ Mục tiêu

- Khởi tạo ứng dụng web viết bằng .NET 8 MVC
- Tạo và đồng bộ mã nguồn lên GitHub
- Cài đặt các công cụ hỗ trợ cần thiết như .NET SDK, AWS CLI
- Thiết lập AWS CodeBuild và kết nối GitHub qua CodeConnections
- Kiểm tra webhook để đảm bảo pipeline có thể tự động kích hoạt khi đẩy mã

## 🧩 Nội dung

Bạn sẽ lần lượt thực hiện các bước sau:

1. [Chuẩn bị ứng dụng .NET MVC](2.1-dotnet-app/)  
   → Tạo một ứng dụng web cơ bản có sẵn một số unit test.

2. [Tạo repository GitHub](2.2-github-repo/)  
   → Đẩy source code lên GitHub để làm nguồn kiểm thử.

3. [Cài đặt các công cụ cần thiết](2.3-install-tools/)  
   → Bao gồm .NET SDK, AWS CLI, Git,...

4. [Tạo project AWS CodeBuild](2.4-codebuild-project/)  
   → Kết nối GitHub với AWS qua CodeConnections và định cấu hình build.

5. [Kiểm tra webhook GitHub](2.5-webhook-verify/)  
   → Đảm bảo khi có thay đổi mã thì pipeline tự động khởi chạy.

---

📌 **Gợi ý:**  
Bạn nên hoàn thành toàn bộ phần này **trước khi tiếp tục phần kiểm thử**, vì các lỗi về môi trường thường là nguyên nhân khiến pipeline CI/CD không hoạt động đúng cách.

> Sau khi hoàn tất, bạn sẽ có một môi trường sẵn sàng để thực hiện kiểm thử tự động với CodeBuild.

---

  
