---
title: "Required Tools Installation"
date: 2025-07-04
weight: 2
chapter: false
pre: "<b>2.2. </b>"
---

## Required Tools Installation

To proceed with automated testing using AWS CodeBuild, you'll need to install and configure several tools.

### 1. AWS CLI Installation

#### For Windows:
1. Download the AWS CLI MSI installer:
   - Visit: https://aws.amazon.com/cli/
   - Download the Windows x64 installer

2. Run the installer:
   - Double-click the downloaded file
   - Follow the installation wizard
   - Verify installation by opening Command Prompt and running:
     ```bash
     aws --version
     ```

#### For Linux:
```bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

#### For macOS:
```bash
brew install awscli
```

### 2. Configure AWS CLI

1. Get your AWS credentials:
   - Access Key ID
   - Secret Access Key
   - Default region (e.g., us-east-1)

2. Run configuration:
   ```bash
   aws configure
   ```

3. Enter your credentials when prompted:
   ```
   AWS Access Key ID: [Your Access Key]
   AWS Secret Access Key: [Your Secret Key]
   Default region name: [Your Region]
   Default output format: json
   ```

### 3. Git Installation (if not already installed)

#### For Windows:
- Download from: https://git-scm.com/download/win
- Run the installer with default options

#### For Linux:
```bash
sudo apt-get update
sudo apt-get install git
```

#### For macOS:
```bash
brew install git
```

### 4. Visual Studio Code (Optional but Recommended)

1. Download VS Code:
   - Visit: https://code.visualstudio.com/
   - Choose your platform version

2. Install recommended extensions:
   - AWS Toolkit
   - C# Dev Kit
   - Git Extension Pack

### Verification Steps

1. Verify AWS CLI:
```bash
aws --version
```

2. Verify Git:
```bash
git --version
```

3. Test AWS Configuration:
```bash
aws sts get-caller-identity
```

### Troubleshooting

1. AWS CLI Issues:
   - Ensure your AWS credentials are correct
   - Check if your IAM user has appropriate permissions
   - Verify your default region is set correctly

2. Git Issues:
   - Make sure Git is in your system's PATH
   - Configure Git with your credentials:
     ```bash
     git config --global user.name "Your Name"
     git config --global user.email "your.email@example.com"
     ```

### Next Steps

After installing and configuring all required tools, proceed to [CodeBuild Project Setup](../2.3-codebuild-project/)
