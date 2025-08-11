---
title: "Verify Automatic Test Results on Code Push"
date: 2025-07-04
weight: 4
chapter: false
pre: "<b>3.4. </b>"
---

In this section, you will push code to GitHub and observe automatic test results from AWS CodeBuild.

---

## 🎯 Objectives

- Push code to GitHub repository
- Watch CodeBuild run tests automatically
- Check test results and reports

---

## 🔧 Implementation Steps

### 1️⃣ Push Code to GitHub

```bash
git add .
git commit -m "Test trigger CodeBuild from GitHub"
git push origin main
```

![Push Code](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/push-code.png)

---

### 2️⃣ Monitor Automatic Build

- Go to AWS CodeBuild console
- Select project `ci-dotnet-unittest`
- Observe new build being automatically created

![Build History](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/build-history.png)

---

### 3️⃣ View Build Details

In the **Build details** tab, you can monitor:

- **Phase details**: Steps being executed
- **Build logs**: Detailed test process logs
- **Environment variables**: Environment variables in use

![Build Details](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/build-details1.png)
![Build Details](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/build-details2.png)
![Build Details](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/build-details3.png)

---

### 4️⃣ Check Test Results in CloudWatch

1. Go to CloudWatch Logs
2. Find CodeBuild Log group
3. View detailed logs of the recent build

![CloudWatch Logs](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/cloudwatch-logs1.png)
![CloudWatch Logs](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/cloudwatch-logs2.png)

In the logs, look for:
```plaintext
Running tests...
Passed!  - Failed: 0, Passed: 2, Skipped: 0
Test Run Successful.
```

---

### 5️⃣ View Test Report in S3

1. Go to configured S3 bucket
2. Find `TestReport` directory
3. Download and open `index.html`

![S3 Report Directory](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/s3-report-dir.png)
![HTML Test Report](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/html-report.png)

---

## 💡 Pro Tips

1. **Monitor build status**:
   - Bookmark build history page
   - Enable email notifications
   - Install AWS CLI for status checks

2. **Effective debugging**:
   ```bash
   # View latest build logs
   aws codebuild batch-get-builds --ids <build-id>
   ```

3. **Time optimization**:
   - Push meaningful code
   - Run tests locally first
   - Verify buildspec syntax

---

## 📝 Notes

- Automatic builds only run on configured branch pushes
- Each push creates a new build
- Logs are stored in CloudWatch
- HTML reports update after each build

{{% notice tip %}}
Always check build status before leaving your computer
{{% /notice %}}
