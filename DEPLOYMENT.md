# Deployment Guide

## Deploying to GitHub Pages

### Step 1: Create a GitHub Repository

1. Go to [GitHub](https://github.com) and log in
2. Click the "+" icon in the top right and select "New repository"
3. Name your repository `personal-website` (or any name you prefer)
4. Make it public
5. Don't initialize with README (we already have one)
6. Click "Create repository"

### Step 2: Push Your Code to GitHub

Open your terminal in VS Code (Terminal → New Terminal) and run:

```bash
# Initialize git repository (if not already done)
git init

# Add all files
git add .

# Commit your changes
git commit -m "Initial commit: Personal portfolio website"

# Add your GitHub repository as remote
git remote add origin https://github.com/GraceInCode/personal-website.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click on "Settings" tab
3. Scroll down to "Pages" in the left sidebar
4. Under "Source", select "Deploy from a branch"
5. Under "Branch", select `main` and `/ (root)`
6. Click "Save"

### Step 4: Access Your Live Site

After a few minutes, your site will be live at:
```
https://graceincode.github.io/personal-website/
```

You can find the exact URL in the GitHub Pages section of your repository settings.

## Updating Your Site

Whenever you make changes:

```bash
# Add your changes
git add .

# Commit with a descriptive message
git commit -m "Update project descriptions"

# Push to GitHub
git push
```

GitHub Pages will automatically rebuild and deploy your site within a few minutes.

## Using VS Code for Development

### Recommended Extensions

1. **Live Server** - Launch a local development server with live reload
   - Install from VS Code Extensions marketplace
   - Right-click `index.html` → "Open with Live Server"

2. **Prettier** - Code formatter
   - Keeps your code clean and consistent

3. **HTML CSS Support** - IntelliSense for CSS
   - Auto-completion for CSS classes

### VS Code Setup

1. Open the project folder:
   ```bash
   cd personal-website
   code .
   ```

2. Install Live Server extension:
   - Press `Ctrl+Shift+X` (or `Cmd+Shift+X` on Mac)
   - Search for "Live Server"
   - Click "Install"

3. Start development:
   - Right-click `index.html`
   - Select "Open with Live Server"
   - Your site will open at `http://localhost:5500`

## Custom Domain (Optional)

To use a custom domain like `graceincode.com`:

1. Buy a domain from a registrar (Namecheap, Google Domains, etc.)
2. Create a file named `CNAME` in your repository root
3. Add your domain to the file:
   ```
   graceincode.com
   ```
4. Configure DNS settings at your registrar:
   - Add an A record pointing to GitHub's IPs:
     - 185.199.108.153
     - 185.199.109.153
     - 185.199.110.153
     - 185.199.111.153
   - Or add a CNAME record pointing to `graceincode.github.io`

5. Wait for DNS propagation (can take up to 24 hours)

## Troubleshooting

### Site not loading after deployment
- Wait 5-10 minutes for initial deployment
- Check GitHub Actions tab for build status
- Ensure GitHub Pages is enabled in settings

### Changes not appearing
- Clear browser cache (Ctrl+Shift+R or Cmd+Shift+R)
- Wait a few minutes for GitHub to rebuild
- Check that you pushed your changes: `git push`

### 404 errors
- Ensure all file paths are relative (no leading `/`)
- Check that file names match exactly (case-sensitive)

## Next Steps

1. Replace placeholder images with actual project screenshots
2. Update GitHub repository links to your actual repos
3. Add more projects as you build them
4. Consider adding a blog section
5. Implement a backend for the contact form (using services like Formspree or EmailJS)

## Resources

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Git Basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics)
- [VS Code Tips](https://code.visualstudio.com/docs/getstarted/tips-and-tricks)
