---
title: "Writing First Unit Test"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>3.1. </b>"
---

In this section, you will create a simple test file to ensure the CI/CD system can run unit tests correctly.

## ✅ Objectives

- Create a simple test file using xUnit
- Simulate test delays for performance testing
- Verify correctness and performance for future parallel execution

## 📁 File Structure

Create file at: `Web.Tests/LuotXemTests.cs`

![UnitTest](/aws-workshop-demo/images/3-automated-unit-test/3.1-codebuild-setup/codeUnitTestLuotXem.png)

```csharp
using System.Threading;
using Xunit;

namespace Web.Tests
{
    public class LuotXemTests
    {
        [Fact]
        public void Fake_LuotXem_Test1()
        {
            Thread.Sleep(1000); // simulate 1 second test duration
            Assert.True(true);
        }

        [Fact]
        public void Fake_LuotXem_Test2()
        {
            Thread.Sleep(1000);
            Assert.True(true);
        }
    }
}
```
## ✅ Verification

Run the following command in the root directory to verify the tests:

```bash
dotnet test
```

Expected output:

```yaml
Passed!  - Failed: 0, Passed: 2, Skipped: 0
```

![UnitTest](/aws-workshop-demo/images/3-automated-unit-test/3.1-codebuild-setup/TestLuotXem.png)

## 📌 Notes

The Thread.Sleep() calls are used to simulate test processing time. You'll see significant improvements when applying Parallel Execution (section 4).
