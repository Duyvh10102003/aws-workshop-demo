---
title: "Website Setup"
date: 2025-07-04
weight: 1
chapter: false
pre: "<b>2.1. </b>"
---

## Website Setup Options

You have two options for setting up the website for this workshop:

### Option A: Using the Sample Movie Website

1. Fork the sample movie website repository:
   - Go to https://github.com/Duyvh10102003/WebsiteXemPhim
   - Click the "Fork" button in the top-right corner
   - Select your GitHub account as the destination

2. Clone your forked repository:
   ```bash
   git clone https://github.com/[YOUR-USERNAME]/WebsiteXemPhim.git
   cd WebsiteXemPhim
   ```

3. Switch to the HoangDuy branch:
   ```bash
   git checkout HoangDuy
   ```

### Option B: Using Your Own Website

If you prefer to use your own website, follow these steps:

1. Create a new GitHub repository:
   - Go to https://github.com/new
   - Name your repository
   - Choose public or private visibility
   - Initialize with a README if desired

2. Push your website code:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/[YOUR-USERNAME]/[YOUR-REPO].git
   git push -u origin main
   ```

### Important Notes

- Ensure your website code is in the root directory of the repository
- The repository must be accessible to AWS CodeBuild
- If using a private repository, additional AWS CodeBuild configuration will be required

### Next Steps

After completing either option, proceed to [Required Tools Installation](../2.2-install-tools/)
