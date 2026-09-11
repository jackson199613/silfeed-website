# Silfeed Website - Deployment Guide

## How It Works

This website uses a **Git → GitHub → Netlify** workflow:

1. **Local**: Edit files in your text editor
2. **Git**: Commit changes to your local repository
3. **GitHub**: Push to GitHub repository
4. **Netlify**: Automatically deploys when new code is pushed

## Setup Instructions

### 1. Initial GitHub Setup (First Time Only)

```bash
# Navigate to project folder
cd silfeed-website

# Configure git (if not done yet)
git config user.name "Your Name"
git config user.email "your.email@example.com"

# Add all files
git add .

# Create initial commit
git commit -m "Initial commit: Silfeed website structure"

# Add remote repository
git remote add origin https://github.com/jackson199613/silfeed-website.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### 2. Netlify Deployment Setup

#### Step 1: Create Netlify Account
- Go to [netlify.com](https://netlify.com)
- Sign up with GitHub account

#### Step 2: Connect Repository
- Click "New site from Git"
- Select GitHub provider
- Authorize Netlify to access your GitHub account
- Select `jackson199613/silfeed-website` repository
- Confirm build settings:
  - **Build command**: (leave empty)
  - **Publish directory**: `.`
- Click "Deploy site"

#### Step 3: Set Custom Domain
- Go to Site settings → Domain management
- Add custom domain: `silfeed.com`
- Update DNS records at your domain registrar

## How to Make Changes

### Workflow for Updates

```bash
# 1. Make changes to files
# Edit index.html, css/main.css, or other files

# 2. Check status
git status

# 3. Stage changes
git add .

# 4. Commit with meaningful message
git commit -m "Update: Changed hero section text"

# 5. Push to GitHub
git push

# 6. Netlify automatically deploys within seconds
# Monitor at: https://app.netlify.com
```

## Common Tasks

### Adding a New Page

```bash
# Create new folder and HTML file
mkdir -p products
touch products/index.html

# Edit products/index.html with content

# Commit
git add products/
git commit -m "Add: Products page"
git push
```

### Updating Styles

```bash
# Edit css/main.css

git add css/main.css
git commit -m "Style: Update button colors"
git push
```

### Adding Images

```bash
# Place image in img/ folder
cp ~/Downloads/image.jpg img/

git add img/image.jpg
git commit -m "Asset: Add product image"
git push
```

## Monitoring & Troubleshooting

### Check Deployment Status
- Netlify Dashboard: https://app.netlify.com
- Recent deploys section shows build logs

### Common Issues

**Build failed?**
- Check Netlify build logs for errors
- Ensure HTML syntax is correct
- Verify all file paths are relative (not absolute)

**Changes not showing?**
- Hard refresh browser: `Ctrl+Shift+R` or `Cmd+Shift+R`
- Wait a few seconds for Netlify build to complete
- Check if commit was actually pushed: `git log`

**Need to rollback?**
- Go to Netlify Dashboard
- Click "Deploys" tab
- Redeploy from previous version

## Git Commands Reference

```bash
# Check git status
git status

# View recent commits
git log --oneline

# Add specific file
git add path/to/file.html

# Add all files
git add .

# Commit changes
git commit -m "Description of changes"

# Push to GitHub
git push

# Pull latest from GitHub
git pull

# Create new branch
git checkout -b feature-name

# Switch branch
git checkout main
```

## Project Structure

```
silfeed-website/
├── index.html              # Main landing page
├── css/
│   └── main.css           # Main stylesheet
├── js/
│   └── main.js            # Main JavaScript
├── img/                   # Images folder
│   ├── logo.svg
│   ├── hero-image.jpg
│   └── ...
├── products/
│   └── index.html         # Products page
├── blog/
│   └── index.html         # Blog/Intelligence
├── case-studies/
│   └── index.html         # Case studies
├── netlify.toml           # Netlify config
├── .gitignore             # Files to ignore
├── README.md              # Project info
└── DEPLOYMENT.md          # This file
```

## Support

- **GitHub Issues**: Report bugs or request features
- **Netlify Support**: https://support.netlify.com
- **Live Site**: https://silfeed.com

---

Last updated: 2026-09-11
Maintained by: Claude + Jackson
