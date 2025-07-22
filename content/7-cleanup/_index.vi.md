---
title: "Dọn dẹp tài nguyên"
date: 2025-07-04
weight: 7
chapter: false
pre: "<b>7. </b>"
---

Để tránh phát sinh chi phí không cần thiết, chúng ta cần xóa các tài nguyên đã tạo trong workshop này.

---

## 🔧 Các bước thực hiện

### 1️⃣ Xóa CodeBuild Project

1. Truy cập [AWS CodeBuild Console](https://console.aws.amazon.com/codebuild)
2. Chọn project **ci-dotnet-unittest**
3. Chọn **Delete** từ menu **Actions**

![Delete CodeBuild](/images/7-cleanup/delete-codebuild.png)
![Delete CodeBuild](/images/7-cleanup/delete-codebuild2.png)

---

### 2️⃣ Xóa CloudWatch Rule

1. Mở [Amazon EventBridge Console](https://console.aws.amazon.com/events)
2. Tìm rule **codebuild-failure-rule**
3. Chọn rule và nhấn **Delete**

![Delete Rule](/images/7-cleanup/delete-rule.png)
![Delete Rule](/images/7-cleanup/delete-rule2.png)
---

### 3️⃣ Xóa SNS Topic

1. Truy cập [Amazon SNS Console](https://console.aws.amazon.com/sns)
2. Chọn topic **test-failure-alerts**
3. Nhấn **Delete**

![Delete SNS](/images/7-cleanup/delete-sns.png)
![Delete SNS](/images/7-cleanup/delete-sns2.png)

---

### 4️⃣ Xóa S3 Bucket

1. Mở [Amazon S3 Console](https://s3.console.aws.amazon.com)
2. Tìm bucket chứa artifacts của CodeBuild
3. Chọn bucket và nhấn **Empty**
4. Sau đó nhấn **Delete**

![Delete S3](/images/7-cleanup/delete-s3.png)
![Delete S3](/images/7-cleanup/delete-s3-2.png)
![Delete S3](/images/7-cleanup/delete-s3-3.png)
![Delete S3](/images/7-cleanup/delete-s3-4.png)
![Delete S3](/images/7-cleanup/delete-s3-5.png)

---

## ✅ Kiểm tra lại

Đảm bảo các tài nguyên sau đã được xóa:

| Dịch vụ | Tài nguyên cần xóa |
|---------|-------------------|
| CodeBuild | Project ci-dotnet-unittest |
| CloudWatch | Rule codebuild-failure-rule |
| SNS | Topic test-failure-alerts |
| S3 | Bucket chứa artifacts |

---

## 🧠 Mẹo

- Sử dụng AWS CLI để xóa nhanh nhiều tài nguyên:

```bash
# Xóa CodeBuild project
aws codebuild delete-project --name ci-dotnet-unittest

# Xóa CloudWatch rule
aws events delete-rule --name codebuild-failure-rule

# Xóa SNS topic
aws sns delete-topic --topic-arn arn:aws:sns:region:account-id:test-failure-alerts

# Xóa S3 bucket (phải empty trước)
aws s3 rm s3://your-bucket-name --recursive
aws s3 rb s3://your-bucket-name
```

---

## ⚠️ Lưu ý quan trọng

- Đảm bảo xóa đúng tài nguyên của workshop
- Kiểm tra kỹ trước khi xóa
- Một số tài nguyên phụ thuộc cần xóa theo thứ tự
- Giữ lại source code trên GitHub nếu muốn tham khảo sau
