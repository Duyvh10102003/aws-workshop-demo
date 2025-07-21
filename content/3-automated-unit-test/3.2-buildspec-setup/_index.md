---
title: "Configure Buildspec for Unit Tests and Report Generation"
date: 2025-07-04
weight: 2
chapter: false
pre: "<b>3.2. </b>"
---

In this step, you will create a `buildspec.yml` file to:

- Install test report generation tools
- Run unit tests with result logging
- Generate readable HTML test reports
- Prepare for result uploading and analysis

## ✅ Objectives

- Install `dotnet-reportgenerator-globaltool`
- Run tests and export logs in `.trx` format
- Generate readable HTML reports

## 📁 Directory Structure

```plaintext
YourProject/
├── src/
│   └── Web/
│       └── Web.Tests/
├── buildspec.yml
└── TestReport/
    └── index.html
```

## 🧾 Buildspec File Content

```yaml
version: 0.2

phases:
  install:
    runtime-versions:
      dotnet: 8.0
    commands:
      - echo === Installing reportgenerator tool ===
      - dotnet tool install -g dotnet-reportgenerator-globaltool
      - export PATH="$PATH:/root/.dotnet/tools"

  build:
    commands:
      - echo === Restoring dependencies ===
      - dotnet restore
      - echo === Building solution ===
      - dotnet build --no-restore
      - echo === Running unit tests ===
      - dotnet test Web.Tests/Web.Tests.csproj --logger "trx;LogFileName=test_results.trx"
      - echo === Generating HTML test report ===
      - reportgenerator "-reports:**/test_results.trx" "-targetdir:TestReport" -reporttypes:Html

artifacts:
  files:
    - TestReport/**/*
  discard-paths: no
```

## 💡 Explanation

| Section | Description |
|---------|-------------|
| dotnet tool install | Installs HTML test report generator tool |
| dotnet test + --logger | Writes test results to .trx file (Test Result XML) |
| reportgenerator | Generates HTML report from .trx file |
| artifacts.files | Specifies outputs to preserve (test reports) |

## 🔄 Implementation Steps

1. Create buildspec.yml in project root
2. Copy buildspec content from guide
3. Commit and push to repository
4. Verify build in CodeBuild

## ✅ Verification

After pushing code, check AWS CodeBuild for:

1. Automatic build trigger
2. Successful phase completion
3. Artifacts containing HTML test report
4. Open TestReport/index.html for detailed results

{{% notice info %}}
Add your test report screenshot here
{{% /notice %}}

## 📌 Notes

- .trx files contain detailed test result information
- HTML reports provide easy result viewing and analysis
- Artifacts are preserved for future reference
- This configuration forms the foundation for integration with other analysis tools
