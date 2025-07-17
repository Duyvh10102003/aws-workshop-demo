---
title: "BuildSpec Setup"
date: 2025-07-04
weight: 2
chapter: false
pre: "<b>3.2. </b>"
---

## Setting up BuildSpec for Test Automation

### Create BuildSpec File
[Insert screenshot: Creating buildspec.yml in VS Code]
1. Create buildspec.yml
   - Create in project root
   - Use basic structure below
   [Insert screenshot: Basic buildspec structure]

2. Basic Configuration
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
   [Insert screenshot: BuildSpec with highlights]

### Configure Test Settings
[Insert screenshot: Test settings configuration]
1. Add Test Options
   - Test logger
   - Results directory
   - Coverage collection
   [Insert screenshot: Test configuration options]

2. Configure Reports
   [Insert screenshot: Report configuration]
   - TRX format
   - Coverage reports
   - Custom reports

### Set Up Artifacts
[Insert screenshot: Artifacts configuration]
1. Configure Output
   - Test results
   - Coverage reports
   - Log files
   [Insert screenshot: Artifacts settings]

### Verification Checklist
- [ ] BuildSpec file created
- [ ] Test configuration added
- [ ] Reports configured
- [ ] Artifacts set up
- [ ] Syntax validated

### Troubleshooting Guide
[Insert screenshot: Common BuildSpec issues]
1. Syntax Errors
   - Check YAML format
   - Verify indentation
   - Validate configuration

2. Build Failures
   - Check phase order
   - Verify commands
   - Review environment

3. Report Issues
   - Check paths
   - Verify permissions
   - Review formats

### Best Practices
[Insert screenshot: BuildSpec best practices]
1. File Organization
   - Clear structure
   - Proper indentation
   - Documented options

2. Configuration
   - Environment variables
   - Conditional steps
   - Error handling

### Next Steps
After setting up BuildSpec, proceed to [Push and Trigger](../3.3-push-trigger/)
