---
title: "Create SNS Topic and Subscribe Email"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>5.1. </b>"
---

## Create SNS Topic

1. Access [Amazon SNS Console](https://console.aws.amazon.com/sns/home)

2. Click **Create topic**
   ![Create Topic Button](/images/5-monitoring/5.1-create-sns/create-topic.png)

3. Fill in topic details:
   - **Type**: Standard
   - **Name**: test-failure-alerts
   - **Display name**: Test Failure Alerts
   
4. Click **Create topic**
   ![Create Topic Button](/images/5-monitoring/5.1-create-sns/create-topic2.png)

5. Save the generated **Topic ARN**:
   ```
   arn:aws:sns:region:account-id:test-failure-alerts
   ```

## Subscribe Email for Notifications

1. In the topic screen, select **Create subscription**
   ![Create Subscription](/images/5-monitoring/5.1-create-sns/create-subscription.png)

2. Configure subscription:
   - **Protocol**: Email
   - **Endpoint**: Enter your email
   ![Subscription Details](/images/5-monitoring/5.1-create-sns/subscription-details.png)

3. Click **Create subscription**

4. Check your email and confirm subscription
   ![Confirm Subscription](/images/5-monitoring/5.1-create-sns/confirm-subscription.png)
   ![Confirm Subscription](/images/5-monitoring/5.1-create-sns/confirm-subscription2.png)
   ![Confirm Subscription](/images/5-monitoring/5.1-create-sns/confirm-subscription3.png)

{{% notice warning %}}
Make sure to confirm your email subscription by clicking the link in the confirmation email. Without confirmation, you won't receive notifications.
{{% /notice %}}
