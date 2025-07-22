---
title: "Kết nối Rule với SNS"
date: 2025-07-04
weight: 3
chapter: false
pre: "<b>5.3. </b>"
---

## Kết nối CloudWatch Rule với SNS Topic

### Thêm SNS Target

1. Trong rule đã tạo, chọn tab **Targets**

2. Click **Add target**
   ![Add Target](/images/5-monitoring/5.3-add-target.png)

3. Cấu hình target:
   - **Target type**: SNS topic
   - **Topic**: test-failure-alerts
   
4. Tùy chỉnh Input transformer:
```json
{
    "build-status": "$.detail.build-status",
    "project-name": "$.detail.project-name",
    "build-id": "$.detail.build-id",
    "logs-url": "https://console.aws.amazon.com/codebuild/home?region=<region>#/builds/<build-id>/view/new"
}
```

### Tùy chỉnh thông báo

1. Định dạng email:
```json
{
    "subject": "CodeBuild Test Failure: ${project-name}",
    "message": "Build ${build-id} has failed.\nStatus: ${build-status}\nView logs: ${logs-url}"
}
```

2. Click **Save**
   ![Message Format](/images/5-monitoring/5.3-message-format.png)

{{% notice info %}}
Input transformer giúp bạn tùy chỉnh nội dung thông báo từ dữ liệu của event.
{{% /notice %}}
