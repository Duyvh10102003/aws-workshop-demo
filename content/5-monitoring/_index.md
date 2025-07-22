---
title: "Test Failure Notifications"
date: 2025-07-04
weight: 5
chapter: false
pre: "<b>5. </b>"
---

In this section, you'll learn how to set up automatic notifications for test failures using Amazon CloudWatch for monitoring and Amazon SNS for notifications.

## 🎯 Objectives

- Create automatic notifications (email, SMS...) when a build fails
- Use Amazon CloudWatch to monitor build status
- Use Amazon SNS (Simple Notification Service) to send alerts
- Help managers/devs know immediately when test errors occur

## 🧱 Implementation Steps

| Step | Brief Description |
|------|------------------|
| 5.1 | Create SNS topic & subscribe email for notifications |
| 5.2 | Create CloudWatch Rule to catch errors from CodeBuild |
| 5.3 | Connect Rule → SNS topic to send alerts |
| 5.4 | Test with failed build and verify email reception |

## 🌐 Architecture Overview

1. CodeBuild executes tests
2. CloudWatch monitors build status
3. When a build failure is detected, CloudWatch Rule is triggered
4. Rule sends notification to SNS Topic
5. SNS sends email to subscribed addresses

{{% children /%}}
