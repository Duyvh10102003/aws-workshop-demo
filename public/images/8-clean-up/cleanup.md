---
title: "Cleanup Instructions"
date: 2025-07-04
weight: 8
chapter: false
pre: "<b>8. </b>"
---

## Resource Cleanup Instructions

### Overview
Follow these steps carefully to remove all resources created during the workshop. The steps are ordered to handle dependencies correctly and prevent any orphaned resources.

### Cleanup Steps

#### 1. CodeBuild Resources

1. Delete CodeBuild projects:
```bash
# List all CodeBuild projects
aws codebuild list-projects

# Delete each project
aws codebuild delete-project --name dotnet-test-automation
aws codebuild delete-project --name performance-test-project
```

2. Remove build artifacts:
```bash
# Delete S3 bucket contents
aws s3 rm s3://test-results-bucket --recursive

# Delete the bucket
aws s3 delete-bucket --bucket test-results-bucket
```

#### 2. CloudWatch Resources

1. Delete log groups:
```bash
# Delete CodeBuild log groups
aws logs delete-log-group --log-group-name /aws/codebuild/test-automation

# Delete test execution log groups
aws logs delete-log-group --log-group-name /aws/test-execution
```

2. Remove CloudWatch dashboards:
```bash
# Delete custom dashboards
aws cloudwatch delete-dashboards --dashboard-names TestAutomationDashboard
```

3. Delete alarms:
```bash
# Delete cost and performance alarms
aws cloudwatch delete-alarms --alarm-names HighTestingCost HighResourceUtilization
```

#### 3. IAM Resources

1. Remove IAM roles:
```bash
# First detach policies
aws iam detach-role-policy \
  --role-name CodeBuildServiceRole \
  --policy-arn arn:aws:iam::aws:policy/AWSCodeBuildAdminAccess

# Then delete role
aws iam delete-role --role-name CodeBuildServiceRole
```

2. Delete custom policies:
```bash
# List and delete custom policies
aws iam list-policies --scope Local
aws iam delete-policy --policy-arn <policy-arn>
```

#### 4. GitHub Integration

1. Remove GitHub connection:
   - Go to AWS CodeBuild console
   - Navigate to Source providers
   - Delete GitHub connection

2. Delete webhooks:
   - Go to GitHub repository settings
   - Navigate to Webhooks
   - Delete AWS CodeBuild webhook

#### 5. Verification Steps

1. Verify resource deletion:
```bash
# Check CodeBuild projects
aws codebuild list-projects

# Check CloudWatch log groups
aws logs describe-log-groups

# Check IAM roles
aws iam list-roles | grep CodeBuild
```

2. Check AWS Cost Explorer:
   - Verify no ongoing charges
   - Check for any remaining resources
   - Monitor billing for next few days

### Best Practices

1. Resource Tracking
   - Maintain resource inventory
   - Document dependencies
   - Use tags effectively
   - Regular audits

2. Cleanup Process
   - Follow dependency order
   - Verify each step
   - Document issues
   - Backup important data

3. Cost Management
   - Monitor billing
   - Set up alerts
   - Regular checks
   - Document expenses

### Common Issues and Solutions

1. Dependency Conflicts
   - Follow correct order
   - Force delete if needed
   - Check dependencies
   - Document errors

2. Permission Issues
   - Verify IAM roles
   - Check permissions
   - Use admin account
   - Document access

3. Resource Lock
   - Check resource state
   - Wait for completion
   - Force termination
   - Document locks

### Final Verification

1. Run verification script:
```bash
#!/bin/bash

echo "Checking CodeBuild resources..."
aws codebuild list-projects

echo "Checking CloudWatch resources..."
aws logs describe-log-groups
aws cloudwatch describe-alarms

echo "Checking IAM resources..."
aws iam list-roles | grep CodeBuild

echo "Checking S3 buckets..."
aws s3 ls | grep test-results

if [ $? -eq 0 ]; then
    echo "Warning: Some resources might still exist"
else
    echo "All resources successfully cleaned up"
fi
```

2. Document cleanup status:
```markdown
# Cleanup Status Report
Date: $(date)
Status: Complete/Incomplete

## Resources Checked
- CodeBuild projects: [Status]
- CloudWatch resources: [Status]
- IAM roles: [Status]
- S3 buckets: [Status]

## Issues Encountered
- [List any issues]

## Follow-up Actions
- [List any required actions]
```

### Next Steps
- Monitor AWS billing for the next billing cycle
- Remove any workshop-related local files
- Document lessons learned
- Update team documentation
