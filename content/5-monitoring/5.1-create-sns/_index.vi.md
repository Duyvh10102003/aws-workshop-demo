---
title: "Tạo SNS Topic và đăng ký email"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>5.1. </b>"
---

### Tạo SNS Topic

1. Truy cập [Amazon SNS Console](https://console.aws.amazon.com/sns/home)

2. Click **Create topic**
   ![Create Topic Button](/aws-workshop-demo/images/5-monitoring/5.1-create-sns/create-topic.png)

3. Điền thông tin:
   - **Type**: Standard
   - **Name**: test-failure-alerts
   - **Display name**: Test Failure Alerts

4. Click **Create**
   ![Create Topic Button](/aws-workshop-demo/images/5-monitoring/5.1-create-sns/create-topic2.png)

### Đăng ký email

1. Trong topic vừa tạo, chọn **Create subscription**
   ![Create Subscription](/aws-workshop-demo/images/5-monitoring/5.1-create-sns/create-subscription.png)
2. Cấu hình:
   - **Protocol**: Email
   - **Endpoint**: your-email@example.com
   ![Subscription Details](/aws-workshop-demo/images/5-monitoring/5.1-create-sns/subscription-details.png)
3. Click **Create subscription**

4. Kiểm tra email và xác nhận đăng ký
   ![Confirm Subscription](/aws-workshop-demo/images/5-monitoring/5.1-create-sns/confirm-subscription.png)
   ![Confirm Subscription](/aws-workshop-demo/images/5-monitoring/5.1-create-sns/confirm-subscription2.png)
   ![Confirm Subscription](/aws-workshop-demo/images/5-monitoring/5.1-create-sns/confirm-subscription3.png)
{{% notice warning %}}
Bạn phải xác nhận email subscription bằng cách click vào link trong email xác nhận.
{{% /notice %}}
