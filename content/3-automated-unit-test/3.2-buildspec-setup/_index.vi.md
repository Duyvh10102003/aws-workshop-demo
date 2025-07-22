---
title: "Cấu hình Buildspec "
date: 2025-07-04
weight: 2
chapter: false
pre: "<b>3.2. </b>"
---

Trong bước này, bạn sẽ tạo file `buildspec.yml` để:

- Cài đặt tool tạo báo cáo test
- Chạy unit test có ghi log kết quả
- Sinh HTML test report dễ xem
- Chuẩn bị sẵn cho các bước upload kết quả hoặc phân tích

## ✅ Mục tiêu

- Cài đặt `dotnet-reportgenerator-globaltool`
- Chạy test và xuất log theo định dạng `.trx`
- Sinh báo cáo HTML dễ đọc

## 📁 Cấu trúc thư mục

```plaintext
YourProject/
├── Web.Tests/
├── buildspec.yml
└── TestReport/
    └── index.html
```

## 🧾 Nội dung file `buildspec.yml`

```yaml
version: 0.2

phases:
  install:
    runtime-versions:
      dotnet: 8.0
    commands:
      - echo === Installing reportgenerator tool ===
      - dotnet tool install -g dotnet-reportgenerator-globaltool
      - export PATH="$PATH:/root/.dotnet/tools"

  build:
    commands:
      - echo === Restoring dependencies ===
      - dotnet restore
      - echo === Building solution ===
      - dotnet build --no-restore
      - echo === Running unit tests ===
      - dotnet test Web.Tests/Web.Tests.csproj --logger "trx;LogFileName=test_results.trx"
      - echo === Generating HTML test report ===
      - reportgenerator "-reports:**/test_results.trx" "-targetdir:TestReport" -reporttypes:Html

artifacts:
  files:
    - TestReport/**/*
  discard-paths: no
```

## 💡 Giải thích

| Mục | Mô tả |
|-----|--------|
| dotnet tool install | Cài đặt tool sinh báo cáo test dưới dạng HTML |
| dotnet test + --logger | Ghi kết quả test ra file .trx (Test Result XML) |
| reportgenerator | Tạo báo cáo HTML từ file .trx |
| artifacts.files | Chỉ định output cần lưu trữ (báo cáo test) |

## 🔄 Các bước thực hiện

1. Tạo file buildspec.yml trong thư mục gốc của dự án
2. Copy nội dung buildspec từ hướng dẫn
3. Commit và push lên repository
4. Kiểm tra build trong CodeBuild

## 📌 Ghi chú

- File .trx chứa thông tin chi tiết về kết quả test
- Báo cáo HTML giúp dễ dàng xem và phân tích kết quả
- Artifacts được lưu lại để tham khảo sau này
- Cấu hình này là nền tảng cho việc tích hợp với các công cụ phân tích khác
