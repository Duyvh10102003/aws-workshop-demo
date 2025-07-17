---
title: "Hướng dẫn Dọn dẹp"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>8.1. </b>"
---

## Hướng dẫn Dọn dẹp Tài nguyên

### Tổng quan
Thực hiện theo các bước sau một cách cẩn thận để xóa tất cả tài nguyên đã tạo trong workshop. Các bước được sắp xếp để xử lý phụ thuộc chính xác và ngăn chặn bất kỳ tài nguyên mồ côi nào.

### Các bước Dọn dẹp

#### 1. Tài nguyên CodeBuild

1. Xóa dự án CodeBuild:
```bash
# Liệt kê tất cả dự án CodeBuild
aws codebuild list-projects

# Xóa từng dự án
aws codebuild delete-project --name dotnet-test-automation
aws codebuild delete-project --name performance-test-project
```

2. Xóa artifacts build:
```bash
# Xóa nội dung bucket S3
aws s3 rm s3://test-results-bucket --recursive

# Xóa bucket
aws s3 delete-bucket --bucket test-results-bucket
```

#### 2. Tài nguyên CloudWatch

1. Xóa nhóm log:
```bash
# Xóa nhóm log CodeBuild
aws logs delete-log-group --log-group-name /aws/codebuild/test-automation

# Xóa nhóm log thực thi kiểm thử
aws logs delete-log-group --log-group-name /aws/test-execution
```

2. Xóa bảng điều khiển CloudWatch:
```bash
# Xóa bảng điều khiển tùy chỉnh
aws cloudwatch delete-dashboards --dashboard-names TestAutomationDashboard
```

3. Xóa cảnh báo:
```bash
# Xóa cảnh báo chi phí và hiệu năng
aws cloudwatch delete-alarms --alarm-names ChiPhiKiemThuCao SuDungTaiNguyenCao
```

#### 3. Tài nguyên IAM

1. Xóa vai trò IAM:
```bash
# Đầu tiên gỡ các policy
aws iam detach-role-policy \
  --role-name CodeBuildServiceRole \
  --policy-arn arn:aws:iam::aws:policy/AWSCodeBuildAdminAccess

# Sau đó xóa vai trò
aws iam delete-role --role-name CodeBuildServiceRole
```

2. Xóa policy tùy chỉnh:
```bash
# Liệt kê và xóa policy tùy chỉnh
aws iam list-policies --scope Local
aws iam delete-policy --policy-arn <policy-arn>
```

#### 4. Tích hợp GitHub

1. Xóa kết nối GitHub:
   - Đi đến AWS CodeBuild console
   - Điều hướng đến Source providers
   - Xóa kết nối GitHub

2. Xóa webhook:
   - Đi đến cài đặt GitHub repository
   - Điều hướng đến Webhooks
   - Xóa webhook AWS CodeBuild

#### 5. Các bước Xác minh

1. Xác minh xóa tài nguyên:
```bash
# Kiểm tra dự án CodeBuild
aws codebuild list-projects

# Kiểm tra nhóm log CloudWatch
aws logs describe-log-groups

# Kiểm tra vai trò IAM
aws iam list-roles | grep CodeBuild
```

2. Kiểm tra AWS Cost Explorer:
   - Xác minh không có chi phí đang diễn ra
   - Kiểm tra bất kỳ tài nguyên còn lại
   - Theo dõi thanh toán trong vài ngày tới

### Các Thực hành Tốt nhất

1. Theo dõi Tài nguyên
   - Duy trì kiểm kê tài nguyên
   - Tài liệu hóa phụ thuộc
   - Sử dụng thẻ hiệu quả
   - Kiểm toán thường xuyên

2. Quy trình Dọn dẹp
   - Tuân theo thứ tự phụ thuộc
   - Xác minh từng bước
   - Ghi chép vấn đề
   - Sao lưu dữ liệu quan trọng

3. Quản lý Chi phí
   - Giám sát thanh toán
   - Thiết lập cảnh báo
   - Kiểm tra thường xuyên
   - Ghi chép chi phí

### Vấn đề Thường gặp và Giải pháp

1. Xung đột Phụ thuộc
   - Tuân theo thứ tự đúng
   - Xóa cưỡng bức nếu cần
   - Kiểm tra phụ thuộc
   - Ghi chép lỗi

2. Vấn đề Quyền
   - Xác minh vai trò IAM
   - Kiểm tra quyền
   - Sử dụng tài khoản admin
   - Ghi chép truy cập

3. Khóa Tài nguyên
   - Kiểm tra trạng thái tài nguyên
   - Đợi hoàn thành
   - Chấm dứt cưỡng bức
   - Ghi chép khóa

### Xác minh Cuối cùng

1. Chạy script xác minh:
```bash
#!/bin/bash

echo "Kiểm tra tài nguyên CodeBuild..."
aws codebuild list-projects

echo "Kiểm tra tài nguyên CloudWatch..."
aws logs describe-log-groups
aws cloudwatch describe-alarms

echo "Kiểm tra tài nguyên IAM..."
aws iam list-roles | grep CodeBuild

echo "Kiểm tra bucket S3..."
aws s3 ls | grep test-results

if [ $? -eq 0 ]; then
    echo "Cảnh báo: Một số tài nguyên có thể vẫn tồn tại"
else
    echo "Tất cả tài nguyên đã được dọn dẹp thành công"
fi
```

2. Tài liệu hóa trạng thái dọn dẹp:
```markdown
# Báo cáo Trạng thái Dọn dẹp
Ngày: $(date)
Trạng thái: Hoàn thành/Chưa hoàn thành

## Tài nguyên Đã Kiểm tra
- Dự án CodeBuild: [Trạng thái]
- Tài nguyên CloudWatch: [Trạng thái]
- Vai trò IAM: [Trạng thái]
- Bucket S3: [Trạng thái]

## Vấn đề Gặp phải
- [Liệt kê các vấn đề]

## Hành động Tiếp theo
- [Liệt kê các hành động cần thiết]
```

### Bước tiếp theo
- Theo dõi thanh toán AWS cho chu kỳ thanh toán tiếp theo
- Xóa bất kỳ file cục bộ nào liên quan đến workshop
- Tài liệu hóa bài học kinh nghiệm
- Cập nhật tài liệu nhóm
