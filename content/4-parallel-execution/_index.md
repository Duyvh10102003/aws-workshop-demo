---
title: "Parallel Test Execution with Multiple Test Files"
date: 2025-07-04
weight: 4
chapter: false
pre: "<b>4. </b>"
---

In this section, you will learn how to split tests into multiple files for independent testing and speed up the CI process through parallel execution. This is particularly useful when the number of tests increases or test execution time becomes lengthy.

---

## 🎯 Objectives

- Separate tests by functionality (`ViewTests`, `PerformanceTests`, etc.)
- Support parallel execution to optimize testing time
- Verify CI triggering capability with split tests

---

## 🧪 Test File Organization Example

### `Web.Tests/ViewTests.cs`

```csharp
using System.Threading;
using Xunit;

namespace Web.Tests
{
    public class ViewTests
    {
        [Fact]
        public void Fake_View_Test1()
        {
            Thread.Sleep(1000); // simulate 1-second test
            Assert.True(true);
        }

        [Fact]
        public void Fake_View_Test2()
        {
            Thread.Sleep(1000);
            Assert.True(true);
        }
    }
}
```

![VS Code ViewTests](/aws-workshop-demo/images/4-parallel-execution/view-tests-vscode.png)
<!-- Need image: Screenshot VS Code showing ViewTests.cs with syntax highlighting -->

### `Web.Tests/PerformanceTests.cs`

```csharp
using System.Threading;
using Xunit;

namespace Web.Tests
{
    public class PerformanceTests
    {
        [Fact]
        public void Fake_Performance_Test1()
        {
            Thread.Sleep(1000); // simulate time-consuming test
            Assert.True(true);
        }

        [Fact]
        public void Fake_Performance_Test2()
        {
            Thread.Sleep(1000);
            Assert.True(true);
        }
    }
}
```

![Performance Test Results](/aws-workshop-demo/images/4-parallel-execution/performance-test-results.png)
<!-- Need image: Screenshot of performance test results -->

## ⚙️ Buildspec Requires No Changes

Since dotnet test automatically detects and runs all test files in Web.Tests, you don't need to modify the buildspec.yml file.

```yaml
- dotnet test Web.Tests/Web.Tests.csproj --logger "trx;LogFileName=test_results.trx"
```

<!-- Need image: Screenshot of CodeBuild configuration -->

## 📦 Advanced Tip: Running Tests in Parallel with Multiple CodeBuilds

For large test suites, you can split them across multiple CodeBuilds by creating multiple projects or dividing test steps in buildspec.yml.

You can also use dotnet test --filter to select specific tests by Category, Class, MethodName, etc.

Example:

```yaml
- dotnet test Web.Tests/Web.Tests.csproj --filter "FullyQualifiedName~PerformanceTests"
- dotnet test Web.Tests/Web.Tests.csproj --filter "FullyQualifiedName~ViewTests"
```

## ✅ Verifying Results

- After pushing code, CodeBuild will automatically run all tests

![Test Results](/aws-workshop-demo/images/4-parallel-execution/test-results.png)

- Open Build history in CodeBuild to view results of each build

![Test Results](/aws-workshop-demo/images/4-parallel-execution/test-results2.png)

- Check test report:
**CodeBuild** → **Build projects** → **Build history** → **ci-dotnet-unittest** → **[Select latest build]** → **Reports** → **[Select latest report]**

![Test Results](/aws-workshop-demo/images/4-parallel-execution/test-results3.png)

## 🧠 Additional Tips

For thread-level parallel testing, you can configure xUnit parallelism:
- Use dotnet test --parallel 
- Or configure in xunit.runner.json

{{% notice tip %}}
For further optimization, you can:
- Group related tests into collections
- Use AWS CodeBuild matrix builds
- Configure test retry for flaky tests
{{% /notice %}}
