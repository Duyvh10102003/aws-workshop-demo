---
title: "CodeBuild Project Setup"
date: 2025-07-04
weight: 3
chapter: false
pre: "<b>2.3. </b>"
---

## Setting Up AWS CodeBuild Project

In this section, we'll create and configure an AWS CodeBuild project that will run our automated tests.

### 1. Create IAM Role for CodeBuild

1. Open the AWS Management Console
2. Navigate to IAM service
3. Create a new role:
   - Select AWS service as the trusted entity
   - Choose CodeBuild as the use case
   - Add these managed policies:
     - AWSCodeBuildAdminAccess
     - AmazonS3FullAccess (for test artifacts)

### 2. Create CodeBuild Project

1. Open AWS CodeBuild console
2. Click "Create build project"
3. Configure project settings:

   **Project configuration**
   ```
   Project name: website-automated-testing
   Description: Automated testing for website using CodeBuild
   ```

   **Source**
   ```
   Source provider: GitHub
   Repository: Select your repository
   Branch: main (or your preferred branch)
   ```

   **Environment**
   ```
   Environment image: Managed image
   Operating system: Ubuntu
   Runtime: Standard
   Image: aws/codebuild/standard:7.0
   Environment type: Linux
   Service role: Use the role created in step 1
   ```

   **Buildspec**
   ```
   Build specifications: Use a buildspec file
   Buildspec name: buildspec.yml
   ```

   **Artifacts**
   ```
   Type: No artifacts
   ```

### 3. Create Basic buildspec.yml

In your repository root, create a file named `buildspec.yml`:

```yaml
version: 0.2

phases:
  install:
    runtime-versions:
      dotnet: 8.0
    commands:
      - echo Installing dependencies...
      
  pre_build:
    commands:
      - echo Pre-build phase...
      
  build:
    commands:
      - echo Build started...
      
  post_build:
    commands:
      - echo Build completed...

reports:
  test-reports:
    files:
      - '**/*'
    base-directory: 'testresults'
    file-format: VisualStudioTrx
```

### 4. Test the Build

1. Save all configurations
2. Click "Start build" in CodeBuild console
3. Monitor the build progress
4. Check build logs for any issues

### Important Notes

1. **Repository Access**:
   - For public repositories: No additional setup needed
   - For private repositories: Configure GitHub authentication

2. **Build Logs**:
   - Available in CloudWatch Logs
   - Retained for 30 days by default

3. **Costs**:
   - CodeBuild charges per minute of build time
   - Free tier includes 100 build minutes per month

### Troubleshooting Common Issues

1. **Build Failures**:
   - Check IAM role permissions
   - Verify buildspec.yml syntax
   - Ensure all required files exist in repository

2. **GitHub Connection Issues**:
   - Verify GitHub connection status
   - Check repository permissions
   - Confirm webhook configuration

### Next Steps

Now that your environment is set up, you can proceed to the next module to start implementing automated tests.
