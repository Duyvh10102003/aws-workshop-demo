---
title: "Tạo CloudWatch Rule"
date: 2025-07-04
weight: 2
chapter: false
pre: "<b>5.2. </b>"
---

## Tạo CloudWatch Rule để theo dõi CodeBuild

### Tạo EventBridge Rule

1. Truy cập [Amazon EventBridge Console](https://console.aws.amazon.com/events)

2. Click **Create rule**
   ![Create Rule](/images/5-monitoring/5.2-create-rule.png)

3. Cấu hình rule:
   - **Name**: codebuild-failure-rule
   - **Description**: Monitor CodeBuild test failures

4. Trong phần **Event pattern**, chọn:
   - **Service**: CodeBuild
   - **Event type**: CodeBuild Build State Change

5. Tùy chỉnh pattern để chỉ bắt các build thất bại:
```json
{
    "source": ["aws.codebuild"],
    "detail-type": ["CodeBuild Build State Change"],
    "detail": {
        "build-status": ["FAILED"]
    }
}
```

![Event Pattern](/images/5-monitoring/5.2-event-pattern.png)

### Cấu hình IAM Role

1. Tạo IAM role cho EventBridge:
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "sns:Publish",
            "Resource": "arn:aws:sns:region:account-id:test-failure-alerts"
        }
    ]
}
```

2. Gắn role với rule vừa tạo

{{% notice tip %}}
Bạn có thể thêm các điều kiện khác vào event pattern như:
- Build timeout
- Memory issues
- Specific project names
{{% /notice %}}
