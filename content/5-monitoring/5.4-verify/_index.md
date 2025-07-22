---
title: "Verify Alert System Operation"
date: 2025-07-04
weight: 4
chapter: false
pre: "<b>5.4. </b>"
---

### Create Failing Test Case

1. Add a failing test case to your project:

```csharp
[Fact]
public void Test_Should_Fail()
{
    Assert.True(false); // This test will always fail
}
```

2. Commit and push code:
```bash
git add .
git commit -m "test: add failing test to verify notifications"
git push
```

### Monitor Process

1. Access CodeBuild console to watch the build
   ![Build Progress](/images/5-monitoring/5.4-verify/build-progress.png)

2. Wait for build failure
   ![Build Failed](/images/5-monitoring/5.4-verify/build-failed.png)

3. Check your email
   ![Email Alert](/images/5-monitoring/5.4-verify/email-alert.png)

{{% notice tip %}}
After confirming the system works, don't forget to fix the test case to avoid affecting the actual pipeline.
{{% /notice %}}
