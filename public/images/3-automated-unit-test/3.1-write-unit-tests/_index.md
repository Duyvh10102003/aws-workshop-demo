---
title: "Write Unit Tests"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>3.1. </b>"
---

## Writing Unit Tests

### Create Test Project
[Insert screenshot: VS Code new test project creation]
1. Create Test Project
   - Open terminal in solution directory
   - Create new xUnit project
   [Insert screenshot: Terminal commands and output]

2. Add Project Reference
   [Insert screenshot: Adding project reference in VS Code]
   - Reference main project
   - Verify reference added
   [Insert screenshot: Project reference confirmation]

### Write Basic Tests
[Insert screenshot: VS Code with test file open]
1. Create Calculator Tests
   ```csharp
   // Simple test example
   public class CalculatorTests
   {
       [Fact]
       public void Add_TwoNumbers_ReturnsSum()
       {
           var calc = new Calculator();
           var result = calc.Add(2, 3);
           Assert.Equal(5, result);
       }
   }
   ```
   [Insert screenshot: Test code with highlights]

### Test Organization
[Insert screenshot: Test project structure]
1. Folder Structure
   - Controllers/
   - Services/
   - Models/
   [Insert screenshot: Organized test folders]

2. Naming Conventions
   [Insert screenshot: Test naming examples]
   - ClassName_MethodName_ExpectedResult
   - Clear and descriptive names

### Run Tests Locally
[Insert screenshot: Test Explorer in VS Code]
1. Using Test Explorer
   - Open Test Explorer
   - Run all tests
   - View results
   [Insert screenshot: Test results display]

2. Using Command Line
   [Insert screenshot: Terminal with test commands]
   ```bash
   dotnet test
   ```

### Verification Checklist
- [ ] Test project created
- [ ] Project reference added
- [ ] Basic tests written
- [ ] Tests run successfully
- [ ] Results displayed correctly

### Troubleshooting Guide
[Insert screenshot: Common test issues]
1. Project Reference Issues
   - Check project path
   - Verify framework version
   - Review dependencies

2. Test Discovery Problems
   - Check test attributes
   - Verify test class public
   - Review naming conventions

3. Test Execution Issues
   - Check runtime errors
   - Verify dependencies
   - Review test context

### Best Practices
[Insert screenshot: Test writing best practices]
1. Test Structure
   - Arrange-Act-Assert pattern
   - Single responsibility
   - Clear assertions

2. Code Organization
   - Logical grouping
   - Consistent naming
   - Proper isolation

### Next Steps
After writing basic tests, proceed to [BuildSpec Setup](../3.2-buildspec-setup/)
