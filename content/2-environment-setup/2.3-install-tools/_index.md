---
title: "Install Required Tools"
date: 2025-07-04
weight: 3
chapter: false
pre: "<b>2.3. </b>"
---

## Installing Required Tools

### AWS CLI Installation
[Insert screenshot: AWS CLI download page]
1. Download AWS CLI
   - Windows: Download MSI installer
   - Linux/macOS: Use package manager
   [Insert screenshot: Download options highlighted]

2. Install AWS CLI
   [Insert screenshot: Installation steps]
   - Run installer
   - Accept terms
   - Choose install location
   - Complete installation

3. Verify Installation
   [Insert screenshot: Terminal showing version check]
   ```bash
   aws --version
   ```

### Configure AWS Credentials
[Insert screenshot: AWS IAM console credentials page]
1. Get Access Keys
   - Open AWS Console
   - Go to IAM
   - Create access key
   [Insert screenshot: Access key creation process]

2. Configure CLI
   [Insert screenshot: AWS configure command]
   ```bash
   aws configure
   ```
   Enter:
   - AWS Access Key ID
   - AWS Secret Access Key
   - Default region
   - Output format

### Install VS Code Extensions
[Insert screenshot: VS Code extensions marketplace]
1. Required Extensions:
   - AWS Toolkit
   - C# Dev Kit
   - .NET Core Test Explorer
   [Insert screenshot: Extension installation buttons]

2. Configure Extensions
   [Insert screenshot: Extension settings]
   - AWS Toolkit settings
   - C# configuration
   - Test Explorer setup

### Verification Checklist
- [ ] AWS CLI installed
- [ ] AWS credentials configured
- [ ] VS Code extensions installed
- [ ] Can run AWS CLI commands
- [ ] Can access AWS services

### Troubleshooting Guide
[Insert screenshot: Common installation issues]
1. AWS CLI Issues
   - Path not found
   - Permission errors
   - Credential errors

2. VS Code Problems
   - Extension conflicts
   - Loading issues
   - Update required

3. AWS Access Issues
   - Invalid credentials
   - Permission denied
   - Region issues

### Best Practices
[Insert screenshot: AWS security best practices]
1. Security
   - Use IAM roles
   - Rotate access keys
   - Minimum permissions

2. Configuration
   - Named profiles
   - Regional settings
   - Default output format

### Next Steps
After installing all required tools, proceed to [CodeBuild Project Setup](../2.4-codebuild-project/)
