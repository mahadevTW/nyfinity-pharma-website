# Nyfinity Pharmaceuticals Website
Official website for Nyfinity Pharmaceuticals.

## Domain
- **Custom Domain:** nyfinity.com
- **GitHub Pages:** Configured for custom domain deployment

## Setup Instructions

### GitHub Pages Configuration
1. Go to your repository settings on GitHub: `https://github.com/YOUR_USERNAME/nyfinity-pharma-website/settings/pages`

2. Under **"Source"**, select:
   - **Branch:** `main`
   - **Folder:** `/ (root)`
   - Click **Save**

3. Under **"Custom domain"**, enter: `nyfinity.com`
   - GitHub will automatically create/update the CNAME file
   - Wait for DNS verification (may take a few minutes)

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

## Notes
- The CNAME file must be in the root directory for custom domain to work
- GitHub Pages serves static files only (HTML, CSS, JavaScript, images)
- Changes pushed to the main branch will automatically deploy to the live site
