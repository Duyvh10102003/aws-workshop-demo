---
title: "Tạo CloudWatch Rule"
date: 2025-07-04
weight: 2
chapter: false
pre: "<b>5.2. </b>"
---

### Tạo EventBridge Rule

1. Truy cập [Amazon EventBridge Console](https://console.aws.amazon.com/events)

2. Click **Create rule**
   ![Create Rule](/images/5-monitoring/5.2-cloudwatch-rule/create-rule.png)

3. Cấu hình rule:
   - **Name**: codebuild-failure-rule
   - **Description**: Monitor CodeBuild test failures
    ![Create Rule](/images/5-monitoring/5.2-cloudwatch-rule/create-rule2.png)

4. Trong phần **Event pattern**, chọn:
   - **Service**: CodeBuild
   - **Event type**: CodeBuild Build State Change
    ![Create Rule](/images/5-monitoring/5.2-cloudwatch-rule/create-rule3.png)
    ![Create Rule](/images/5-monitoring/5.2-cloudwatch-rule/create-rule4.png)
    - Chọn **Next**
