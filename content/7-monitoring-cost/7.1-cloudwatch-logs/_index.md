---
title: "CloudWatch Logs"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>7.1. </b>"
---

## Setting Up CloudWatch Logs

### Configure Log Groups
[Insert screenshot: CloudWatch log groups setup]
1. Create Log Groups
   ```bash
   aws logs create-log-group --log-group-name /aws/codebuild/test-automation
   aws logs put-retention-policy --log-group-name /aws/codebuild/test-automation --retention-in-days 30
   ```
   [Insert screenshot: Log group creation]

2. Configure Log Streams
   [Insert screenshot: Log streams setup]
   - Build logs
   - Test execution logs
   - Performance metrics

### Set Up Metrics
[Insert screenshot: Metrics configuration]
1. Create Metric Filters
   ```bash
   aws logs put-metric-filter \
     --log-group-name /aws/codebuild/test-automation \
     --filter-name test-duration \
     --filter-pattern "[timestamp, duration]" \
     --metric-transformations \
         metricName=TestDuration,metricNamespace=TestAutomation,metricValue=$duration
   ```
   [Insert screenshot: Metric filter creation]

2. Configure Dashboards
   [Insert screenshot: Dashboard setup]
   - Cost metrics
   - Resource usage
   - Test execution stats

### Set Up Alerts
[Insert screenshot: Alert configuration]
1. Create CloudWatch Alarms
   - Cost thresholds
   - Resource limits
   - Error rates
   [Insert screenshot: Alarm creation]

2. Configure Notifications
   [Insert screenshot: Notification setup]
   - Email alerts
   - SNS topics
   - Integration webhooks

### Verification Checklist
- [ ] Log groups created
- [ ] Metrics configured
- [ ] Dashboards set up
- [ ] Alerts working
- [ ] Retention policies set

### Troubleshooting Guide
[Insert screenshot: Common logging issues]
1. Log Collection Issues
   - Missing logs
   - Delayed delivery
   - Permission problems

2. Metric Problems
   - Filter matching
   - Data aggregation
   - Calculation errors

3. Alert Issues
   - Notification delivery
   - Threshold settings
   - Integration failures

### Best Practices
[Insert screenshot: Logging best practices]
1. Log Management
   - Structured logging
   - Clear categories
   - Proper retention

2. Metric Configuration
   - Relevant metrics
   - Proper aggregation
   - Useful dimensions

### Next Steps
After setting up CloudWatch logs, proceed to [Analyze Cost](../7.2-analyze-cost/)
