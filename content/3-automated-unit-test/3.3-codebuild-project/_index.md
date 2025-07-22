---
title: "Setting up CodeBuild to Run Unit Tests"
date: 2025-07-04
weight: 3
chapter: false
pre: "<b>3.3. </b>"
---

In this section, you will create a CodeBuild project to automatically run unit tests from your GitHub source code, using the `buildspec.yml` file configured in the previous step.

---

## 🎯 Objectives

- Create a project in AWS CodeBuild
- Connect GitHub with AWS
- Configure build environment
- Run `buildspec.yml` from repository
- (Optional) Store test reports in Amazon S3

---

## 🔧 Implementation Steps

### 1️⃣ Access AWS CodeBuild

- Open: [https://console.aws.amazon.com/codebuild/home](https://console.aws.amazon.com/codebuild/home)
- Click **Create build project**

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/CreateCodeBuilder.png)

---

### 2️⃣ Enter Project Information

- **Project name**: `ci-dotnet-unittest`
- **Description**: `Run unit tests and generate HTML report`

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/CreateProject.png)

---

### 3️⃣ Configure Source

1. In the **Source** section, select **Source provider** as **GitHub (Version 2)** and select **Manage account credentials** if you haven't connected GitHub yet.

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/Source.png)

2. Click **create a new GitHub connection** to start creating connection

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github1.png)

3. A new window will open. Enter a name for the connection:

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github2.png)

4. Select **Install a new app** to connect to your GitHub

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github3.png)

5. Enter your GitHub password to connect

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github4.png)

6. After successful connection, you'll see a confirmation message

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github5.png)

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github6.png)

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github7.png)

7. Return to the **Manage default source credential** page, select the connection you just created

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github8.png)

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github9.png)

8. Back to CodeBuild page, select the connected repository and choose your project's main branch (usually `main` or `master`)

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/connect-github10.png)

9. In **Primary source webhook events** section, ✅ Check "Rebuild every time a code change is pushed to this repository"

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/webhook.png)

---

### 4️⃣ Setup Build Environment

- **Provisioning model**: `On-demand`
- **Environment image**: `Managed image`
- **Compute**: `EC2`
- **Running mode**: `Container`
- **Operating System**: `Amazon Linux`
- **Runtime**: `Standard`
- **Image**: `aws/codebuild/amazonlinux-x86_64-standard:5.0`

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/environment.png)

---

### 5️⃣ Buildspec file

- **Buildspec**: select `Use a buildspec file`
- Ensure your repo has `buildspec.yml` in the root directory

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/buildspec.png)

---

### 6️⃣ (Optional) Artifact for Reports

- If you want to store HTML test reports:
  - **Artifacts type**: `Amazon S3`
  - **S3 bucket**: select previously created bucket

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/S3.png)

---

### 7️⃣ Create Project

- Click **Create build project**
- After creation:
  - You can select **Start build** to test
  - Or push code to GitHub for webhook to run automatically

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/Cloudwatch.png)

![CodeBuilder](/images/3-automated-unit-test/3.3-codebuild-project/doneCreate.png)

---

## 💡 Pro Tips

- If your repo lacks a `buildspec.yml`, you can use "Insert build commands", but it's not recommended
- After project creation, AWS will run tests automatically on "Start build" or push (if webhook enabled)
- With GitHub version 2, repos appear in a dropdown. PAT requires manual token entry
