---
title: "Kiểm tra hoạt động cảnh báo"
date: 2025-07-04
weight: 4
chapter: false
pre: "<b>5.4. </b>"
---

### Tạo test case thất bại

1. Thêm một test case sẽ fail vào project:

```csharp
[Fact]
public void Test_Should_Fail()
{
    Assert.True(false); // Test này sẽ luôn fail
}
```

2. Commit và push code:
```bash
git add .
git commit -m "test: add failing test to verify notifications"
git push
```

### Theo dõi quá trình

1. Truy cập CodeBuild console để xem build
   ![Build Progress](/aws-workshop-demo/images/5-monitoring/5.4-verify/build-progress.png)

2. Đợi build thất bại
   ![Build Failed](/aws-workshop-demo/images/5-monitoring/5.4-verify/build-failed.png)

3. Kiểm tra email
   ![Email Alert](/aws-workshop-demo/images/5-monitoring/5.4-verify/email-alert.png)

{{% notice tip %}}
Sau khi xác nhận hệ thống hoạt động, đừng quên sửa lại test case để không ảnh hưởng tới pipeline thực tế.
{{% /notice %}}
