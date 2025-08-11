---
title: "Tối ưu kiểm thử song song với nhiều file test"
date: 2025-07-04
weight: 4
chapter: false
pre: "<b>4. </b>"
---

Trong phần này, bạn sẽ học cách chia nhỏ các bài test ra nhiều file để kiểm thử độc lập và tăng tốc quá trình CI bằng cách thực thi song song. Điều này đặc biệt hữu ích khi số lượng test tăng lên hoặc thời gian test kéo dài.

---

## 🎯 Mục tiêu

- Tách riêng các test theo chức năng (`LuotXemTests`, `PerformanceTests`, …)
- Hỗ trợ chạy song song để tối ưu thời gian kiểm thử
- Kiểm tra khả năng trigger CI với các test chia nhỏ

---

## 🧪 Ví dụ tổ chức file test

### `Web.Tests/LuotXemTests.cs`

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

![VS Code LuotXemTests](/aws-workshop-demo/images/4-parallel-execution/luotxem-tests-vscode.png)
<!-- Cần thêm ảnh: Screenshot VS Code showing LuotXemTests.cs với syntax highlighting -->

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
            Thread.Sleep(1000); // giả lập test tốn thời gian
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
<!-- Cần thêm ảnh: Screenshot kết quả test hiệu năng -->

## ⚙️ Buildspec không cần thay đổi

Vì dotnet test sẽ tự động phát hiện và chạy tất cả các file test trong Web.Tests, nên bạn không cần thay đổi file buildspec.yml.

```yaml
- dotnet test Web.Tests/Web.Tests.csproj --logger "trx;LogFileName=test_results.trx"
```

<!-- Cần thêm ảnh: Screenshot cấu hình CodeBuild -->

## 📦 Gợi ý mở rộng: Chạy test song song bằng nhiều CodeBuild (nâng cao)

Nếu số lượng test quá lớn, bạn có thể chia ra nhiều CodeBuild chạy theo nhóm test khác nhau bằng cách tạo nhiều project hoặc chia bước test trong buildspec.yml thành nhiều dòng.

Cũng có thể dùng dotnet test --filter để chọn test cụ thể theo Category, Class, MethodName, …

Ví dụ:

```yaml
- dotnet test Web.Tests/Web.Tests.csproj --filter "FullyQualifiedName~PerformanceTests"
- dotnet test Web.Tests/Web.Tests.csproj --filter "FullyQualifiedName~LuotXemTests"
```

## ✅ Kiểm tra kết quả

- Sau khi push code, CodeBuild sẽ tự động chạy lại toàn bộ test

![Test Results](/aws-workshop-demo/images/4-parallel-execution/test-results.png)

- Mở mục Build history trong CodeBuild để xem kết quả từng lần build

![Test Results](/aws-workshop-demo/images/4-parallel-execution/test-results2.png)

- Kiểm tra báo cáo test:
**CodeBuild** → **Build projects** → **Build history** → **ci-dotnet-unittest** → **[Chọn bản build gần nhất]**→ **Reports** → **[Chọn bản report gần nhất]**

![Test Results](/aws-workshop-demo/images/4-parallel-execution/test-results3.png)

## 🧠 Mẹo thêm

Nếu muốn test song song ở cấp độ thread, bạn có thể cấu hình xUnit parallelism:
- Dùng dotnet test --parallel 
- Hoặc chỉnh trong xunit.runner.json

{{% notice tip %}}
Để tối ưu hơn nữa, bạn có thể:
- Nhóm các test liên quan vào cùng collection
- Sử dụng AWS CodeBuild matrix builds
- Cấu hình test retry cho các test không ổn định
{{% /notice %}}
