---
title: "Tạo SNS Topic"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>5.1. </b>"
---

## Tạo SNS Topic và đăng ký email

### Tạo SNS Topic

1. Truy cập [Amazon SNS Console](https://console.aws.amazon.com/sns/home)

2. Click **Create topic**
   ![Create Topic](/images/5-monitoring/5.1-create-topic.png)

3. Điền thông tin:
   - **Type**: Standard
   - **Name**: test-failure-alerts
   - **Display name**: Test Failure Alerts

4. Click **Create**
   ![Topic Details](/images/5-monitoring/5.1-topic-details.png)

### Đăng ký email

1. Trong topic vừa tạo, chọn **Create subscription**

2. Cấu hình:
   - **Protocol**: Email
   - **Endpoint**: your-email@example.com

3. Click **Create subscription**

4. Kiểm tra email và xác nhận đăng ký

{{% notice warning %}}
Bạn phải xác nhận email subscription bằng cách click vào link trong email xác nhận.
{{% /notice %}}
