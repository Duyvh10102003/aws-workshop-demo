---
title: ".NET Application Setup"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>2.1. </b>"
---

## Setting up the .NET Application

### Installation Steps
[Insert screenshot: .NET SDK download page]
1. Download .NET 8 SDK
   - Visit https://dotnet.microsoft.com/download
   - Select .NET 8 SDK
   - Choose your operating system
   [Insert screenshot: Download options with highlighted buttons]

2. Install SDK
   [Insert screenshot: Installation wizard steps]
   - Run the installer
   - Follow installation wizard
   - Accept default options
   - Wait for completion

3. Verify Installation
   [Insert screenshot: Command prompt with version check]
   ```bash
   dotnet --version
   ```
   Expected output: 8.0.x

### Create Test Project
[Insert screenshot: VS Code new project creation]
1. Open Terminal/Command Prompt
2. Navigate to your workspace
3. Create new MVC project:
   ```bash
   dotnet new mvc -n TestAutomationDemo
   ```
   [Insert screenshot: Project creation output]

### Project Structure
[Insert screenshot: VS Code project structure]
Your project should include:
- Controllers/
- Models/
- Views/
- wwwroot/
- Program.cs
- appsettings.json

### Verification Checklist
- [ ] .NET SDK installed successfully
- [ ] Project creates without errors
- [ ] Can build project (`dotnet build`)
- [ ] Can run project (`dotnet run`)
- [ ] Can access homepage (https://localhost:5001)

### Troubleshooting Guide
[Insert screenshot: Common errors and solutions]
1. SDK Not Found
   - Verify PATH environment variable
   - Reinstall SDK if needed
   
2. Port Already in Use
   - Check running applications
   - Change port in launchSettings.json

3. Build Errors
   - Clear NuGet cache
   - Restore packages
   - Check SDK version

### Next Steps
After verifying your .NET setup, proceed to [GitHub Repository Setup](../2.2-github-repo/)
