---
title: "Create S3 Bucket"
date: 2025-07-04
weight: 3
chapter: false
pre: "<b>2.3. </b>"
---

# 🪣 Create S3 Bucket

In this section, you will create an S3 bucket to store test reports from AWS CodeBuild.

---

## 🔧 Implementation Steps

### 1️⃣ Access Amazon S3

1. Log in to AWS Console
2. Find and select **S3** service

![Access S3](/aws-workshop-demo/images/2-environment-setup/2.3-create-s3/access-s3.jpg)

### 2️⃣ Create Bucket

1. Click **Create bucket**
2. Enter bucket name: `dotnet-unit-test-report`
3. Keep other settings as default
4. Click **Create bucket**

![Create Bucket](/aws-workshop-demo/images/2-environment-setup/2.3-create-s3/create-bucket.png)

![Create Bucket](/aws-workshop-demo/images/2-environment-setup/2.3-create-s3/create-bucket2.png)

### 3️⃣ Verify

- New bucket appears in the list
- Bucket status shows "Created"

![Bucket Created](/aws-workshop-demo/images/2-environment-setup/2.3-create-s3/bucket-created.png)

---

## 📝 Notes

- This bucket will be used to store test reports from CodeBuild
- Bucket name must be globally unique
- Default settings are sufficient for workshop purposes
