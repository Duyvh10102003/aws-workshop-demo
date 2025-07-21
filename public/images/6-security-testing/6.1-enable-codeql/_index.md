---
title: "Enable CodeQL"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>6.1. </b>"
---

## Enabling CodeQL Analysis

### Set Up CodeQL Environment
[Insert screenshot: CodeQL setup]
1. Configure GitHub Repository
   - Enable GitHub Actions
   - Configure security settings
   - Set up permissions
   [Insert screenshot: GitHub configuration]

2. Create CodeQL Workflow
   ```yaml
   name: "CodeQL Analysis"
   
   on:
     push:
       branches: [ main ]
     pull_request:
       branches: [ main ]
     schedule:
       - cron: '0 0 * * 0'
   
   jobs:
     analyze:
       runs-on: ubuntu-latest
       steps:
         - name: Checkout code
           uses: actions/checkout@v2
         
         - name: Initialize CodeQL
           uses: github/codeql-action/init@v2
           with:
             languages: csharp
   ```
   [Insert screenshot: Workflow configuration]

### Configure Analysis Settings
[Insert screenshot: Analysis configuration]
1. Set Up Query Suites
   - Select security queries
   - Configure custom queries
   - Set analysis scope
   [Insert screenshot: Query configuration]

2. Configure Build Integration
   [Insert screenshot: Build integration]
   - Build settings
   - Analysis triggers
   - Result handling

### Set Up Notifications
[Insert screenshot: Notification setup]
1. Configure Alerts
   - Security alerts
   - Workflow notifications
   - Team notifications
   [Insert screenshot: Alert configuration]

### Verification Checklist
- [ ] CodeQL enabled
- [ ] Workflow configured
- [ ] Queries selected
- [ ] Notifications set
- [ ] Integration tested

### Troubleshooting Guide
[Insert screenshot: Common CodeQL issues]
1. Setup Issues
   - Permission problems
   - Configuration errors
   - Integration failures

2. Analysis Problems
   - Build failures
   - Query errors
   - Resource constraints

3. Notification Issues
   - Alert delivery
   - Configuration problems
   - Access rights

### Best Practices
[Insert screenshot: CodeQL best practices]
1. Configuration
   - Regular updates
   - Clear documentation
   - Proper scoping

2. Analysis Management
   - Regular reviews
   - Performance monitoring
   - Result tracking

### Next Steps
After enabling CodeQL, proceed to [Review Alerts](../6.2-review-alerts/)
