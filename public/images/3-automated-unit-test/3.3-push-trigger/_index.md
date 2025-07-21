---
title: "Push and Trigger"
date: 2025-07-04
weight: 3
chapter: false
pre: "<b>3.3. </b>"
---

## Push Changes and Trigger Tests

### Prepare Changes
[Insert screenshot: VS Code with changes]
1. Review Changes
   - Check modified files
   - Verify test files
   - Review buildspec
   [Insert screenshot: Git changes in VS Code]

2. Stage Changes
   [Insert screenshot: Staging changes]
   ```bash
   git add .
   git status
   ```

### Commit and Push
[Insert screenshot: Commit dialog]
1. Create Commit
   ```bash
   git commit -m "feat: add automated tests"
   ```
   [Insert screenshot: Commit confirmation]

2. Push to GitHub
   ```bash
   git push origin main
   ```
   [Insert screenshot: Push success]

### Monitor Build
[Insert screenshot: CodeBuild console]
1. Watch Build Progress
   - Open CodeBuild console
   - Find latest build
   - Monitor phases
   [Insert screenshot: Build progress]

2. Check Build Logs
   [Insert screenshot: Build logs]
   - View real-time logs
   - Check test execution
   - Monitor results

### Verification Checklist
- [ ] Changes pushed successfully
- [ ] Build triggered automatically
- [ ] Tests executing correctly
- [ ] Results being reported
- [ ] Logs available

### Troubleshooting Guide
[Insert screenshot: Common issues]
1. Push Issues
   - Check credentials
   - Verify remote
   - Review permissions

2. Trigger Problems
   - Check webhook
   - Verify build configuration
   - Review IAM roles

3. Build Failures
   - Check environment
   - Review dependencies
   - Verify test setup

### Best Practices
[Insert screenshot: Best practices]
1. Code Management
   - Regular commits
   - Clear messages
   - Feature branches

2. Build Monitoring
   - Watch progress
   - Check logs
   - Verify results

### Next Steps
After confirming successful triggers, proceed to [View Results](../3.4-view-results/)
