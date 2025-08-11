---
title: "Tự động quét bảo mật với CodeQL"
date: 2025-07-04
weight: 6
chapter: false
pre: "<b>6. </b>"
---

Bạn sẽ cấu hình GitHub Actions để tự động **kiểm tra lỗi bảo mật trong source code .NET**. Tất cả hoàn toàn tự động, chạy mỗi khi bạn **push code hoặc mở Pull Request**.

---

## 🎯 Mục tiêu

- Bật sẵn workflow "CodeQL" trong GitHub
- Không cần code gì thêm
- Kiểm tra lỗi bảo mật trực tiếp trên GitHub

---

## 🔧 Các bước cấu hình

### 1️⃣ Mở tab **Actions** trên GitHub

- Truy cập trang repo của bạn
- Nhấn vào tab **"Actions"** (nằm trên thanh menu ngang)

![Open Actions Tab](/aws-workshop-demo/images/6-security-testing/open-actions.png)
![Select CodeQL](/aws-workshop-demo/images/6-security-testing/open-actions2.png)

---

### 2️⃣ Bật workflow sẵn có tên là **"CodeQL Analysis"**

- Tìm mục **"Security → Code scanning → CodeQL Analysis"**
- Nhấn **"Configure"**
![Select CodeQL](/aws-workshop-demo/images/6-security-testing/select-codeql.png)


---

### 3️⃣ Nhấn **Start commit**

- Giữ nguyên file như mặc định
- Nhấn nút **"Start commit" → Commit directly to main**
- GitHub sẽ tự tạo file `.github/workflows/codeql.yml` cho bạn

![Start Commit](/aws-workshop-demo/images/6-security-testing/start-commit.png)
![Start Commit](/aws-workshop-demo/images/6-security-testing/start-commit2.png)

---

### 4️⃣ Chờ workflow chạy

- Vào lại tab **Actions**, thấy workflow "CodeQL" đang chạy
- Mất khoảng 1–2 phút để phân tích

![Workflow Running](/aws-workshop-demo/images/6-security-testing/workflow-running.png)

---

### 5️⃣ Xem kết quả bảo mật

- Vào tab **"Security" > "Code scanning alerts"**
- Nếu có lỗi bảo mật trong code (như SQL injection, lỗi null, hardcoded password, ...), GitHub sẽ liệt kê chi tiết tại đây

![Security Alerts](/aws-workshop-demo/images/6-security-testing/security-alerts.png)

---

## 🧠 Mẹo thêm

- CodeQL tự hiểu repo là C#/.NET, bạn không cần khai báo thêm
- Có thể bật CodeQL cho tất cả các nhánh (sửa phần `branches:` trong `codeql.yml`)
- Muốn quét định kỳ (dù không push)? CodeQL hỗ trợ `schedule`

---

## 📘 Tài liệu thêm

- [Code scanning alerts](https://docs.github.com/en/code-security/code-scanning)
- [CodeQL GitHub Action](https://github.com/github/codeql-action)
