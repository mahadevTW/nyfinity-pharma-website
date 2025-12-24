# GitHub Pages Setup Checklist for nyfinity.com

## Current Status: 404 Error on nyfinity.com
This means DNS is working (pointing to GitHub), but the site isn't configured yet.

## Step-by-Step Fix:

### ✅ Step 1: Verify Repository Exists on GitHub
1. Go to: `https://github.com/YOUR_USERNAME/nyfinity-pharma-website`
2. **Check:** Can you see the repository?
   - ❌ If NO → Create it first (see Step 2)
   - ✅ If YES → Continue to Step 3

### ✅ Step 2: Create Repository (If needed)
1. Go to https://github.com/new
2. Repository name: `nyfinity-pharma-website`
3. Make it **Public** (required for free GitHub Pages)
4. **DO NOT** check "Add a README file" (we already have one)
5. Click "Create repository"

### ✅ Step 3: Push Files to GitHub
Open terminal in your project folder and run:

```bash
# Check if git is initialized
git status

# If not initialized, run:
git init
git add .
git commit -m "Initial commit - Nyfinity website"

# Add remote (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/nyfinity-pharma-website.git

# Push to GitHub
git branch -M main
git push -u origin main
```

**Verify:** Go to your GitHub repository and check:
- ✅ `index.html` is visible
- ✅ `CNAME` file is visible (should contain `nyfinity.com`)
- ✅ `README.md` is visible

### ✅ Step 4: Enable GitHub Pages
1. Go to: `https://github.com/YOUR_USERNAME/nyfinity-pharma-website/settings/pages`
2. Under **"Source"**:
   - Select **Branch:** `main` (or `master` if that's your default)
   - Select **Folder:** `/ (root)`
   - Click **"Save"**
3. **Wait 1-2 minutes** for GitHub to build
4. You should see:
   - ✅ Green checkmark
   - ✅ Message: "Your site is live at https://YOUR_USERNAME.github.io/nyfinity-pharma-website/"

### ✅ Step 5: Configure Custom Domain
1. Still in **Settings → Pages**
2. Scroll to **"Custom domain"** section
3. Enter: `nyfinity.com`
4. Click **"Save"**
5. GitHub will verify DNS (may take a few minutes)

### ✅ Step 6: Verify CNAME File in Repository
1. Go to your repository: `https://github.com/YOUR_USERNAME/nyfinity-pharma-website`
2. Check if `CNAME` file exists
3. Click on `CNAME` file
4. It should contain: `nyfinity.com`
5. If it doesn't exist or is wrong:
   - Make sure your local `CNAME` file has `nyfinity.com`
   - Push it: `git add CNAME && git commit -m "Add CNAME" && git push`

### ✅ Step 7: Wait and Test
1. Wait 5-10 minutes after enabling Pages
2. Visit: `https://nyfinity.com`
3. If still 404, check:
   - Repository is Public
   - GitHub Pages is enabled
   - `index.html` exists in repository
   - CNAME file exists in repository

## Common Issues:

### Issue: "Repository not found"
- **Fix:** Make sure repository exists and is Public

### Issue: "No files in repository"
- **Fix:** Push your files using `git push`

### Issue: "GitHub Pages not enabled"
- **Fix:** Go to Settings → Pages and enable it

### Issue: "CNAME file missing"
- **Fix:** Make sure CNAME file is pushed to GitHub

### Issue: "Still seeing 404 after setup"
- **Fix:** Wait 5-10 minutes, clear browser cache, try incognito mode

## Quick Verification Commands:

```bash
# Check if files are committed
git status

# Check remote repository
git remote -v

# Check if CNAME exists locally
cat CNAME

# Push any uncommitted changes
git add .
git commit -m "Update files"
git push
```

