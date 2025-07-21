---
title: "Viết Unit Test đầu tiên"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>3.1. </b>"
---

Trong phần này, bạn sẽ tạo một file test đơn giản để đảm bảo hệ thống CI/CD có thể chạy unit test đúng cách.

## ✅ Mục tiêu

- Tạo test file đơn giản sử dụng xUnit
- Giả lập quá trình test có độ trễ
- Kiểm tra tính đúng đắn và hiệu năng khi chạy test song song sau này

## 📁 Các bước thực hiện

Tạo file tại: `Web.Tests/LuotXemTests.cs`

![UnitTest](/images/3-automated-unit-test/3.1-codebuild-setup/codeUnitTestLuotXem.png)

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
            Thread.Sleep(1000); // giả lập test mất 1 giây
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

## ✅ Kiểm tra

Chạy lệnh sau trong thư mục gốc để kiểm tra test:

```bash
dotnet test
```

Kết quả mong đợi:

```yaml
Passed!  - Failed: 0, Passed: 2, Skipped: 0
```

![UnitTest](/images/3-automated-unit-test/3.1-codebuild-setup/TestLuotXem.png)

## 📌 Ghi chú

Các Thread.Sleep() được sử dụng để mô phỏng thời gian xử lý của test. Bạn sẽ thấy hiệu quả rõ rệt khi áp dụng Parallel Execution (phần 4).
