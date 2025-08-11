---
title: "Automated Security Scanning with CodeQL"
date: 2025-07-04
weight: 6
chapter: false
pre: "<b>6. </b>"
---

You'll configure GitHub Actions to automatically **check for security vulnerabilities in your .NET source code**. Everything runs automatically when you **push code or open a Pull Request**.

---

## 🎯 Objectives

- Enable the built-in "CodeQL" workflow in GitHub
- No additional coding required
- Check security issues directly on GitHub

---

## 🔧 Configuration Steps

### 1️⃣ Open **Actions** tab on GitHub

- Access your repository page
- Click the **"Actions"** tab (in the top menu bar)

![Open Actions Tab](/aws-workshop-demo/images/6-security-testing/open-actions.png)
![Select CodeQL](/aws-workshop-demo/images/6-security-testing/open-actions2.png)

---

### 2️⃣ Enable the **"CodeQL Analysis"** workflow

- Find **"Security → Code scanning → CodeQL Analysis"**
- Click **"Set up this workflow"**

![Select CodeQL](/aws-workshop-demo/images/6-security-testing/select-codeql.png)

---

### 3️⃣ Click **Start commit**

- Keep the file as default
- Click **"Commit changes" → Commit directly to main**
- GitHub will create `.github/workflows/codeql.yml` for you

![Start Commit](/aws-workshop-demo/images/6-security-testing/start-commit.png)
![Start Commit](/aws-workshop-demo/images/6-security-testing/start-commit2.png)

---

### 4️⃣ Wait for workflow to run

- Go back to **Actions** tab, see "CodeQL" workflow running
- Takes about 1-2 minutes to analyze

![Workflow Running](/aws-workshop-demo/images/6-security-testing/workflow-running.png)

---

### 5️⃣ View security results

- Go to **"Security" > "Code scanning alerts"**
- If there are security issues in the code (like SQL injection, null errors, hardcoded passwords, ...), GitHub will list them here

![Security Alerts](/aws-workshop-demo/images/6-security-testing/security-alerts.png)

---

## ✅ Summary

| Step | Description |
|------|------------|
| 1 | Open Actions tab in GitHub |
| 2 | Select "CodeQL Analysis" workflow |
| 3 | Click "Start commit" to enable |
| 4 | Workflow runs after push |
| 5 | Check Security tab for alerts |

---

## 🧠 Additional Tips

- CodeQL automatically detects C#/.NET repos, no extra configuration needed
- Can enable CodeQL for all branches (modify `branches:` in `codeql.yml`)
- Want periodic scans (even without pushes)? CodeQL supports `schedule`

---

## 📘 Further Reading

- [Code scanning alerts](https://docs.github.com/en/code-security/code-scanning)
- [CodeQL GitHub Action](https://github.com/github/codeql-action)
