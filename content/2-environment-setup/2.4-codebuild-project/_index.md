---
title: "CodeBuild Project Setup"
date: 2025-07-04
weight: 4
chapter: false
pre: "<b>2.4. </b>"
---

## Setting up AWS CodeBuild Project

### Create CodeBuild Project
[Insert screenshot: AWS CodeBuild console]
1. Open AWS Console
   - Go to CodeBuild service
   - Click "Create build project"
   [Insert screenshot: Create project button]

2. Project Configuration
   [Insert screenshot: Project settings form]
   - Project name: `dotnet-test-automation`
   - Source provider: GitHub
   - Repository: Select your repository
   [Insert screenshot: Source settings highlighted]

3. Environment Setup
   [Insert screenshot: Environment configuration]
   - Operating system: Ubuntu
   - Runtime: Standard
   - Image: aws/codebuild/amazonlinux2-x86_64-standard:4.0
   [Insert screenshot: Environment options]

### Configure Build Settings
[Insert screenshot: Build configuration page]
1. Create buildspec.yml
   - Basic configuration shown below
   - Full configuration in next module
   ```yaml
   version: 0.2
   phases:
     install:
       runtime-versions:
         dotnet: 8.0
     build:
       commands:
         - dotnet build
         - dotnet test
   ```

2. Artifacts Configuration
   [Insert screenshot: Artifacts settings]
   - Type: No artifacts
   - Enable logs in CloudWatch

### IAM Role Setup
[Insert screenshot: IAM role creation]
1. Create Service Role
   - Role will be created automatically
   - Review permissions
   - Add additional permissions if needed

### Verification Checklist
- [ ] Project created successfully
- [ ] GitHub connection working
- [ ] Environment configured
- [ ] IAM role created
- [ ] Basic build successful

### Troubleshooting Guide
[Insert screenshot: Common CodeBuild issues]
1. GitHub Connection Issues
   - Check OAuth token
   - Verify permissions
   - Review connection status

2. Build Failures
   - Check buildspec syntax
   - Verify environment
   - Review IAM permissions

3. Environment Problems
   - Image compatibility
   - Resource limits
   - Runtime versions

### Best Practices
[Insert screenshot: CodeBuild best practices]
1. Security
   - Minimal IAM permissions
   - Secure environment variables
   - Regular updates

2. Performance
   - Appropriate compute size
   - Cache configuration
   - Build optimization

### Next Steps
After setting up CodeBuild, proceed to [Webhook Verification](../2.5-webhook-verify/)
