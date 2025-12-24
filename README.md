# Nyfinity Pharmaceuticals Website
Official website for Nyfinity Pharmaceuticals.

## Domain
- **Custom Domain:** nyfinity.com
- **GitHub Pages:** Configured for custom domain deployment

## Setup Instructions

### Step 1: Initialize Git Repository (If not already done)
```bash
# Navigate to your project directory
cd /Users/scalevista/projects/nyfinity-pharma-website

# Initialize git (if not already initialized)
git init

# Add all files
git add .

# Commit files
git commit -m "Initial commit - Nyfinity Pharmaceuticals website"

# Add remote repository (replace YOUR_USERNAME with your GitHub username)
git remote add origin https://github.com/YOUR_USERNAME/nyfinity-pharma-website.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 2: Create GitHub Repository
1. Go to [GitHub](https://github.com) and sign in
2. Click the **"+"** icon in the top right → **"New repository"**
3. Repository name: `nyfinity-pharma-website`
4. Make it **Public** (required for free GitHub Pages)
5. **DO NOT** initialize with README, .gitignore, or license (we already have these)
6. Click **"Create repository"**

### Step 3: Push Your Code to GitHub
If you haven't pushed yet, use the commands from Step 1. Make sure all files are committed and pushed:
```bash
git add .
git commit -m "Add website files"
git push -u origin main
```

### Step 4: Enable GitHub Pages
1. Go to your repository on GitHub: `https://github.com/YOUR_USERNAME/nyfinity-pharma-website`
2. Click on **"Settings"** tab (top menu)
3. Scroll down to **"Pages"** in the left sidebar
4. Under **"Source"**, select:
   - **Branch:** `main`
   - **Folder:** `/ (root)` or `/`
   - Click **"Save"**
5. Wait 1-2 minutes for GitHub to build your site
6. You should see a green checkmark and a message: **"Your site is live at https://YOUR_USERNAME.github.io/nyfinity-pharma-website/"**

### Step 5: Configure Custom Domain
1. Still in **Settings → Pages**
2. Under **"Custom domain"**, enter: `nyfinity.com`
3. Click **"Save"**
4. GitHub will automatically create/update the CNAME file in your repository
5. Wait for DNS verification (may take a few minutes)

**Important:** After entering the custom domain, you may need to:
- Pull the updated CNAME file: `git pull origin main`
- Or verify the CNAME file exists in your repository

### DNS Configuration
Configure the following DNS records with your domain registrar for **nyfinity.com**:

#### Option 1: A Records (Recommended)

| Type | Name | Value | TTL |
|------|------|-------|-----|
| A | @ | 185.199.108.153 | 3600 |
| A | @ | 185.199.109.153 | 3600 |
| A | @ | 185.199.110.153 | 3600 |
| A | @ | 185.199.111.153 | 3600 |

#### Option 2: CNAME Record

| Type | Name | Value | TTL |
|------|------|-------|-----|
| CNAME | @ | YOUR_USERNAME.github.io | 3600 |

**Note:** Some registrars don't support CNAME for root domains. Use A records in that case.

### SSL Certificate
GitHub Pages automatically provisions SSL certificates for custom domains. After DNS propagation (usually 24-48 hours), GitHub will enable HTTPS automatically.

### Verification
After setup:
- Visit `https://nyfinity.com` (may take up to 24 hours for DNS propagation)
- Check that the site loads correctly
- Verify HTTPS is enabled (green padlock in browser)

## Local Development
Simply open `index.html` in a web browser or use a local server:

```bash
# Using Python
python3 -m http.server 8000

# Using Node.js (if you have http-server installed)
npx http-server
```

Then visit `http://localhost:8000`

## Repository Structure
```
nyfinity-pharma-website/
├── index.html          # Main website file
├── CNAME               # Custom domain configuration
├── README.md           # This file
└── .gitignore          # Git ignore file
```

## Troubleshooting

### Error: "There isn't a GitHub Pages site here"

This error usually means one of the following:

1. **Repository not created yet:**
   - Make sure you've created the repository on GitHub first
   - Repository must be **Public** (free accounts) or you need GitHub Pro for private repos

2. **Files not pushed to GitHub:**
   - Check that `index.html` exists in your repository
   - Go to your repository URL and verify you can see `index.html` file
   - If not, push your files: `git add . && git commit -m "Add files" && git push`

3. **GitHub Pages not enabled:**
   - Go to **Settings → Pages**
   - Make sure **Source** is set to `main` branch and `/ (root)` folder
   - Click **Save** and wait 1-2 minutes

4. **Wrong repository:**
   - Make sure you're in the correct repository settings
   - URL should be: `https://github.com/YOUR_USERNAME/nyfinity-pharma-website/settings/pages`

5. **Branch name issue:**
   - If your default branch is `master` instead of `main`, select `master` in the Source dropdown
   - Or rename branch: `git branch -M main`

### Verify Your Setup
- ✅ Repository exists on GitHub
- ✅ `index.html` is visible in the repository
- ✅ GitHub Pages is enabled in Settings → Pages
- ✅ Source branch is selected (main or master)
- ✅ You see a green checkmark in Settings → Pages

## Notes
- The CNAME file must be in the root directory for custom domain to work
- GitHub Pages serves static files only (HTML, CSS, JavaScript, images)
- Changes pushed to the main branch will automatically deploy to the live site
- After enabling Pages, wait 1-2 minutes for the site to build
