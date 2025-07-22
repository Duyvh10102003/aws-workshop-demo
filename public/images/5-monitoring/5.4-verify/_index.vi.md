---
title: "Kiểm tra hoạt động"
date: 2025-07-04
weight: 4
chapter: false
pre: "<b>5.4. </b>"
---

## Kiểm tra hoạt động của hệ thống cảnh báo

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
   ![Build Progress](/images/5-monitoring/5.4-build-progress.png)

2. Đợi build thất bại
   ![Build Failed](/images/5-monitoring/5.4-build-failed.png)

3. Kiểm tra email
   ![Email Alert](/images/5-monitoring/5.4-email-alert.png)

### Xác nhận các thành phần

✅ Kiểm tra các điểm sau:

1. **CodeBuild**:
   - Build đã thất bại
   - Log hiển thị test failure

2. **CloudWatch**:
   - Rule đã được trigger
   - Event được ghi nhận

3. **SNS**:
   - Message được gửi thành công
   - Email được nhận với đúng format

{{% notice tip %}}
Sau khi xác nhận hệ thống hoạt động, đừng quên sửa lại test case để không ảnh hưởng tới pipeline thực tế.
{{% /notice %}}
