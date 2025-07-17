---
title: "GitHub Repository Setup"
date: 2025-07-04
weight: 2
chapter: false
pre: "<b>2.2. </b>"
---

## Setting up GitHub Repository

### Create Repository
[Insert screenshot: GitHub new repository page]
1. Login to GitHub
   - Go to github.com
   - Click "+" icon in top right
   - Select "New repository"
   [Insert screenshot: New repository button highlighted]

2. Configure Repository
   [Insert screenshot: Repository settings form]
   - Name: `dotnet-test-automation`
   - Description: "AWS CodeBuild Test Automation Demo"
   - Visibility: Public
   - Initialize with README: No
   [Insert screenshot: Configuration options highlighted]

### Initialize Local Repository
[Insert screenshot: VS Code terminal with git commands]
1. Open project folder in terminal
2. Initialize git:
   ```bash
   git init
   git branch -M main
   ```

### Connect to GitHub
[Insert screenshot: GitHub repository URL location]
1. Add remote:
   ```bash
   git remote add origin https://github.com/<your-username>/dotnet-test-automation.git
   ```

2. Push code:
   ```bash
   git add .
   git commit -m "Initial commit"
   git push -u origin main
   ```
   [Insert screenshot: Successful push output]

### Branch Protection
[Insert screenshot: Branch protection settings page]
1. Go to repository Settings
2. Select Branches
3. Add rule for `main`:
   - Require pull request reviews
   - Require status checks
   - Include administrators
   [Insert screenshot: Protection rules configuration]

### Verification Checklist
- [ ] Repository created successfully
- [ ] Local repository initialized
- [ ] Code pushed to GitHub
- [ ] Branch protection configured
- [ ] Can view code on GitHub

### Troubleshooting Guide
[Insert screenshot: Common GitHub errors and solutions]
1. Authentication Issues
   - Check GitHub credentials
   - Verify SSH keys
   - Use personal access token

2. Push Failures
   - Check remote URL
   - Verify branch name
   - Resolve conflicts

3. Permission Issues
   - Verify repository access
   - Check user permissions
   - Review organization settings

### Next Steps
After setting up your GitHub repository, proceed to [Install Required Tools](../2.3-install-tools/)
