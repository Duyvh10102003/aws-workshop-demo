---
title: "Resource Cleanup"
date: 2025-07-04
weight: 7
chapter: false
pre: "<b>7. </b>"
---

To avoid unnecessary charges, we need to delete all resources created during this workshop.

---

## 🔧 Implementation Steps

### 1️⃣ Delete CodeBuild Project

1. Access [AWS CodeBuild Console](https://console.aws.amazon.com/codebuild)
2. Select project **ci-dotnet-unittest**
3. Choose **Delete** from **Actions** menu

![Delete CodeBuild](/aws-workshop-demo/images/7-cleanup/delete-codebuild.png)

---

### 2️⃣ Delete CloudWatch Rule

1. Open [Amazon EventBridge Console](https://console.aws.amazon.com/events)
2. Find rule **codebuild-failure-rule**
3. Select rule and click **Delete**

![Delete Rule](/aws-workshop-demo/images/7-cleanup/delete-rule.png)

---

### 3️⃣ Delete SNS Topic

1. Access [Amazon SNS Console](https://console.aws.amazon.com/sns)
2. Select topic **test-failure-alerts**
3. Click **Delete**

![Delete SNS](/aws-workshop-demo/images/7-cleanup/delete-sns.png)

---

### 4️⃣ Delete S3 Bucket

1. Open [Amazon S3 Console](https://s3.console.aws.amazon.com)
2. Find bucket containing CodeBuild artifacts
3. Select bucket and click **Empty**
4. Then click **Delete**

![Delete S3](/aws-workshop-demo/images/7-cleanup/delete-s3.png)

---

## ✅ Verification

Ensure the following resources are deleted:

| Service | Resource to Delete |
|---------|-------------------|
| CodeBuild | Project ci-dotnet-unittest |
| CloudWatch | Rule codebuild-failure-rule |
| SNS | Topic test-failure-alerts |
| S3 | Artifacts bucket |

---

## 🧠 Tips

- Use AWS CLI for quick deletion of multiple resources:

```bash
# Delete CodeBuild project
aws codebuild delete-project --name ci-dotnet-unittest

# Delete CloudWatch rule
aws events delete-rule --name codebuild-failure-rule

# Delete SNS topic
aws sns delete-topic --topic-arn arn:aws:sns:region:account-id:test-failure-alerts

# Delete S3 bucket (must empty first)
aws s3 rm s3://your-bucket-name --recursive
aws s3 rb s3://your-bucket-name
```

---

## ⚠️ Important Notes

- Ensure you're deleting the correct workshop resources
- Double-check before deletion
- Some dependent resources need to be deleted in order
- Keep GitHub source code if you want to reference later
