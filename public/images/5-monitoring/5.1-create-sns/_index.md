---
title: "Create SNS Topic"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>5.1. </b>"
---

# Create SNS Topic and Subscribe Email

## Create SNS Topic

1. Access [Amazon SNS Console](https://console.aws.amazon.com/sns/home)

2. Click **Create topic**
   ![Create Topic Button](/images/5-monitoring/5.1-create-topic.png)

3. Fill in topic details:
   - **Type**: Standard
   - **Name**: test-failure-alerts
   - **Display name**: Test Failure Alerts

4. Click **Create topic**
   ![Topic Details](/images/5-monitoring/5.1-topic-details.png)

5. Save the generated **Topic ARN**:
   ```
   arn:aws:sns:region:account-id:test-failure-alerts
   ```

## Subscribe Email for Notifications

1. In the topic screen, select **Create subscription**
   ![Create Subscription](/images/5-monitoring/5.1-create-subscription.png)

2. Configure subscription:
   - **Protocol**: Email
   - **Endpoint**: Enter your email
   ![Subscription Details](/images/5-monitoring/5.1-subscription-details.png)

3. Click **Create subscription**

4. Check your email and confirm subscription
   ![Confirm Subscription](/images/5-monitoring/5.1-confirm-subscription.png)

## Using AWS CLI

You can also perform these steps using AWS CLI:

1. Create topic:
```bash
aws sns create-topic --name test-failure-alerts
```

2. Subscribe email:
```bash
aws sns subscribe \
    --topic-arn arn:aws:sns:region:account-id:test-failure-alerts \
    --protocol email \
    --notification-endpoint your-email@example.com
```

## Verify Setup

- ✅ SNS topic created
- ✅ Email subscription confirmed
- ✅ Topic ARN saved for next step

{{% notice warning %}}
Make sure to confirm your email subscription by clicking the link in the confirmation email. Without confirmation, you won't receive notifications.
{{% /notice %}}
