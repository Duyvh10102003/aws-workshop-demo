---
title: "Kiểm tra kết quả Test tự động khi Push code"
date: 2025-07-04
weight: 4
chapter: false
pre: "<b>3.4. </b>"
---

Trong phần này, bạn sẽ thực hiện push code lên GitHub và xem kết quả test tự động từ AWS CodeBuild.

---

## 🎯 Mục tiêu

- Push code lên GitHub repository
- Xem CodeBuild tự động chạy test
- Kiểm tra kết quả và báo cáo test

---

## 🔧 Các bước thực hiện

### 1️⃣ Push code lên GitHub

```bash
git add .
git commit -m "Test trigger CodeBuild from GitHub"
git push origin main
```

![Push Code](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/push-code.png)

---

### 2️⃣ Theo dõi Build tự động

- Vào AWS CodeBuild console
- Chọn project `ci-dotnet-unittest`
- Quan sát build mới tự động được tạo

![Build History](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/build-history.png)

---

### 3️⃣ Xem chi tiết quá trình Build

Trong tab **Build details**, bạn có thể theo dõi:

- **Phase details**: Các bước đang chạy
- **Build logs**: Log chi tiết của quá trình test
- **Environment variables**: Biến môi trường được sử dụng

![Build Details](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/build-details1.png)
![Build Details](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/build-details2.png)
![Build Details](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/build-details3.png)

---

### 4️⃣ Kiểm tra kết quả Test trong CloudWatch

1. Vào CloudWatch Logs
2. Tìm Log group của CodeBuild
3. Xem chi tiết log của build vừa chạy

![CloudWatch Logs](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/cloudwatch-logs1.png)
![CloudWatch Logs](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/cloudwatch-logs2.png)

Trong log, tìm đoạn:
```plaintext
Running tests...
Passed!  - Failed: 0, Passed: 2, Skipped: 0
Test Run Successful.
```

---

### 5️⃣ Xem báo cáo Test trong S3

1. Vào S3 bucket đã cấu hình
2. Tìm thư mục `TestReport`
3. Tải về và mở file `index.html`

![S3 Report Directory](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/s3-report-dir.png)
![HTML Test Report](/aws-workshop-demo/images/3-automated-unit-test/3.4-verify-results/html-report.png)

---

## 💡 Mẹo

1. **Theo dõi build status**:
   - Bookmark trang build history
   - Bật thông báo email
   - Cài đặt AWS CLI để check status

2. **Debug hiệu quả**:
   ```bash
   # Xem log của build gần nhất
   aws codebuild batch-get-builds --ids <build-id>
   ```

3. **Tối ưu thời gian**:
   - Push code có ý nghĩa
   - Chạy test local trước
   - Kiểm tra buildspec syntax

---

## 📝 Ghi chú

- Build tự động chỉ chạy khi push vào branch được cấu hình
- Mỗi push sẽ tạo một build mới
- Log được lưu trong CloudWatch
- Báo cáo HTML được cập nhật sau mỗi lần build

{{% notice tip %}}
Luôn kiểm tra status của build trước khi rời khỏi máy tính
{{% /notice %}}
