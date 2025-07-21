---
title: "Parallel Test Execution"
date: 2025-07-04
weight: 4
chapter: false
pre: "<b>4. </b>"
---

## Thực thi test song song với AWS CodeBuild

Trong module này, chúng ta sẽ cấu hình thực thi song song các test case để giảm thời gian chạy test tổng thể.

### Cấu hình AWS CodeBuild

1. Tạo file buildspec.yml:
```yaml
version: 0.2

phases:
  install:
    runtime-versions:
      nodejs: 18
    commands:
      - npm install
      
  build:
    commands:
      - echo "Bắt đầu chạy test song song"
      - |
        npm run test:components & \
        npm run test:api & \
        npm run test:e2e & \
        wait
        
  post_build:
    commands:
      - node scripts/merge-test-results.js

reports:
  test-reports:
    files:
      - 'reports/**/*'
    file-format: JunitXml

artifacts:
  files:
    - reports/**/*
    - coverage/**/*
```

### Cấu hình Script trong package.json

```json
{
  "scripts": {
    "test:components": "jest --config jest.components.config.js --maxWorkers=2",
    "test:api": "jest --config jest.api.config.js --maxWorkers=2",
    "test:e2e": "cypress run --parallel --record --key your-key",
    "test:all": "npm-run-all --parallel test:*"
  }
}
```

### Script gộp kết quả test

```javascript
// scripts/merge-test-results.js
const fs = require('fs');

async function mergeResults() {
  const results = {
    components: require('../reports/component-results.json'),
    api: require('../reports/api-results.json'),
    e2e: require('../reports/e2e-results.json')
  };

  const summary = {
    totalTests: 0,
    passed: 0,
    failed: 0,
    duration: 0
  };

  Object.values(results).forEach(result => {
    summary.totalTests += result.totalTests;
    summary.passed += result.passedTests;
    summary.failed += result.failedTests;
    summary.duration += result.duration;
  });

  fs.writeFileSync('reports/summary.json', JSON.stringify(summary, null, 2));
}

mergeResults();
```

### Lợi ích của thực thi song song

1. Giảm thời gian chạy test
   - Chạy nhiều test cùng lúc
   - Tận dụng tối đa tài nguyên

2. Tối ưu tài nguyên
   - Sử dụng hiệu quả AWS CodeBuild
   - Tiết kiệm chi phí

### Các bước thực hiện

1. Tổ chức test theo loại:
```
tests/
├── components/
│   ├── MovieCard.test.js
│   └── MovieList.test.js
├── api/
│   ├── movieService.test.js
│   └── authService.test.js
└── e2e/
    ├── browse.spec.js
    └── watch.spec.js
```

2. Cấu hình Jest cho từng loại test:
```javascript
// jest.components.config.js
module.exports = {
  testMatch: ['<rootDir>/tests/components/**/*.test.js'],
  // ... các cấu hình khác
};

// jest.api.config.js
module.exports = {
  testMatch: ['<rootDir>/tests/api/**/*.test.js'],
  // ... các cấu hình khác
};
```

3. Cấu hình Cypress cho E2E test:
```javascript
// cypress.config.js
module.exports = {
  e2e: {
    setupNodeEvents(on, config) {},
    specPattern: 'tests/e2e/**/*.spec.js',
    supportFile: 'tests/e2e/support/index.js'
  }
};
```

### Giám sát và báo cáo

1. Tích hợp với CloudWatch:
```yaml
# buildspec.yml bổ sung
env:
  variables:
    CLOUDWATCH_NAMESPACE: "MovieApp/Tests"

phases:
  post_build:
    commands:
      - aws cloudwatch put-metric-data --namespace ${CLOUDWATCH_NAMESPACE} --metric-name TestDuration --value $DURATION
      - aws cloudwatch put-metric-data --namespace ${CLOUDWATCH_NAMESPACE} --metric-name TestsPassed --value $PASSED_TESTS
```

2. Tạo Dashboard theo dõi:
- Thời gian chạy test
- Tỷ lệ test pass/fail
- Số lượng test thực thi

### Bước tiếp theo
- Chuyển sang phần Performance Testing
- Cấu hình thông báo kết quả test
- Thiết lập giám sát liên tục
