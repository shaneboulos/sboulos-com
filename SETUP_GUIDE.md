# Setup Guide for sboulos-portfolio

This guide will walk you through setting up, running, and deploying your portfolio website step-by-step.

## ✅ What's Been Created

Your complete Astro portfolio with:
- Clean, minimal design using Space Mono typeface
- Four sections: About/Hero, Projects, Skills, and Contact
- Responsive layout that works on all devices
- Professional styling for e-commerce director roles
- Ready for Cloudflare Pages deployment

## 📋 Step 1: Install Dependencies

Since npm was blocked in my environment, you'll need to install the dependencies on your machine with admin credentials.

1. Open your terminal (Command Prompt, PowerShell, or Terminal)

2. Navigate to the project folder:
```bash
cd path/to/sboulos-portfolio
```

3. **Authenticate as admin** (since you mentioned admin credentials are needed)

4. Install dependencies:
```bash
npm install
```

**What this does**: Downloads Astro and all required packages from npm. This might take 1-2 minutes.

**Expected output**: You should see a progress bar and eventually a message like "added X packages" with no errors.

---

## 🚀 Step 2: Test Locally

Before deploying, let's make sure everything works on your computer.

1. Start the development server:
```bash
npm run dev
```

2. **What this does**: Starts a local web server so you can preview your site

3. **Expected output**: You should see something like:
```
🚀 astro  v4.16.18 started in XXms

  ┃ Local    http://localhost:4321/
  ┃ Network  use --host to expose
```

4. Open your browser and go to: `http://localhost:4321`

5. **What to check**:
   - Does the site load?
   - Is Space Mono font displaying?
   - Do all four sections appear (About, Projects, Skills, Contact)?
   - Does navigation work when clicking nav links?
   - Is it responsive? (try resizing your browser window)

6. To stop the server, press `Ctrl + C` in the terminal

---

## 📝 Step 3: Customize Your Content

Before deploying, you'll want to update the placeholder content with your actual information.

### Update the Hero/About Section
**File**: `src/components/Hero.astro`

Change:
- Your name (if "Shane Boulos" needs adjustment)
- Your title/subtitle
- Your bio description

### Update Projects
**File**: `src/components/Projects.astro`

- Replace the example projects with your actual projects
- Update descriptions, technologies used
- Add or remove projects as needed

### Update Skills
**File**: `src/components/Skills.astro`

- Modify skill categories to match your expertise
- Add/remove specific skills
- Reorganize categories if needed

### Update Contact Information
**File**: `src/components/Contact.astro`

- Update email address (currently: shane@sboulos.com)
- Update LinkedIn URL (currently placeholder)
- Update GitHub URL (currently placeholder)
- Add or remove contact methods

**After making changes**: The dev server will auto-reload, so just refresh your browser to see updates!

---

## 🔧 Step 4: Initialize Git Repository

Now let's set up version control.

1. Make sure you're in the project folder:
```bash
cd path/to/sboulos-portfolio
```

2. Initialize Git:
```bash
git init
```

**What this does**: Creates a new Git repository in your project folder.

3. Add all files to Git:
```bash
git add .
```

**What this does**: Stages all your files for the first commit (the `.gitignore` file ensures we skip `node_modules` and other unnecessary files).

4. Create your first commit:
```bash
git commit -m "Initial commit: Professional portfolio with Astro"
```

**What this does**: Saves a snapshot of your project.

**Expected output**: Should show files changed and insertions.

---

## 🌐 Step 5: Create GitHub Repository

1. Go to [github.com](https://github.com) and sign in

2. Click the "+" icon in the top right → "New repository"

3. **Repository settings**:
   - **Repository name**: `sboulos-portfolio` (or your preferred name)
   - **Description**: "Professional portfolio for Shane Boulos"
   - **Visibility**: Public (required for free Cloudflare Pages)
   - **DO NOT** initialize with README, .gitignore, or license (we already have these)

4. Click "Create repository"

5. **Copy the remote URL** shown (looks like: `https://github.com/yourusername/sboulos-portfolio.git`)

---

## 📤 Step 6: Push to GitHub

1. Add the remote repository (replace with YOUR URL from Step 5):
```bash
git remote add origin https://github.com/yourusername/sboulos-portfolio.git
```

**What this does**: Connects your local Git repository to GitHub.

2. Push your code:
```bash
git branch -M main
git push -u origin main
```

**What this does**:
- Renames your default branch to "main"
- Uploads all your code to GitHub

**Expected output**: Should show upload progress and "Branch 'main' set up to track remote branch 'main'".

3. **Verify**: Refresh your GitHub repository page - you should see all your files!

---

## ☁️ Step 7: Deploy to Cloudflare Pages

### 7.1: Sign up for Cloudflare (if you haven't already)

1. Go to [dash.cloudflare.com/sign-up](https://dash.cloudflare.com/sign-up)
2. Create a free account
3. Verify your email

### 7.2: Create a New Pages Project

1. Log in to Cloudflare Dashboard
2. Click "Workers & Pages" in the left sidebar
3. Click "Create application"
4. Click "Pages" tab
5. Click "Connect to Git"

### 7.3: Connect GitHub

1. Click "Connect GitHub"
2. Authorize Cloudflare to access your GitHub account
3. Select **only** the `sboulos-portfolio` repository (or "All repositories" if you prefer)
4. Click "Install & Authorize"

### 7.4: Configure Build Settings

You'll see a setup page. Configure as follows:

- **Project name**: `sboulos-portfolio` (this will become part of your URL)
- **Production branch**: `main`
- **Framework preset**: Select "Astro" from the dropdown
- **Build command**: `npm run build` (should auto-fill)
- **Build output directory**: `dist` (should auto-fill)

**Environment Variables**:
- Click "Add variable"
- Name: `NODE_VERSION`
- Value: `18` or `20`

### 7.5: Deploy!

1. Click "Save and Deploy"

2. **What happens**: Cloudflare will:
   - Clone your GitHub repository
   - Install dependencies (`npm install`)
   - Build your site (`npm run build`)
   - Deploy to their global CDN

3. **Wait for deployment**: This usually takes 1-3 minutes

4. **Success!** You'll see a success message with your site URL like:
   `https://sboulos-portfolio.pages.dev`

5. Click the URL to view your live site!

---

## 🎯 Step 8: Connect Custom Domain (sboulos.com)

### 8.1: Add Your Domain to Cloudflare

If your domain is not already on Cloudflare:

1. In Cloudflare Dashboard, click "Websites" → "Add a site"
2. Enter `sboulos.com`
3. Select the Free plan
4. Cloudflare will scan your DNS records
5. Update your domain's nameservers at your registrar to Cloudflare's nameservers
6. Wait for DNS propagation (can take 24-48 hours, but often faster)

### 8.2: Connect Domain to Pages

1. Go to "Workers & Pages" → Your project (`sboulos-portfolio`)
2. Click the "Custom domains" tab
3. Click "Set up a custom domain"
4. Enter: `sboulos.com`
5. Click "Continue"
6. Cloudflare will automatically configure DNS
7. Click "Activate domain"

**Optional**: Add `www.sboulos.com` as well following the same steps.

**DNS propagation**: May take a few minutes to a few hours.

---

## 🔄 Step 9: Making Updates

Whenever you want to update your portfolio:

1. Make changes to your local files
2. Test locally: `npm run dev`
3. Commit changes:
```bash
git add .
git commit -m "Description of changes"
```
4. Push to GitHub:
```bash
git push
```
5. **Automatic deployment**: Cloudflare Pages will automatically detect the push and redeploy!

---

## 🛠️ Troubleshooting

### Issue: `npm install` fails
- Make sure you're authenticated as admin
- Check your internet connection
- Try clearing npm cache: `npm cache clean --force`

### Issue: Site doesn't load locally
- Make sure port 4321 isn't already in use
- Try: `npm run dev -- --port 3000` to use a different port

### Issue: Cloudflare build fails
- Check the build logs in Cloudflare Dashboard
- Ensure `NODE_VERSION` environment variable is set to `18` or higher
- Verify GitHub repository has all files committed

### Issue: Fonts not loading
- Check browser console for errors (F12)
- Verify Google Fonts link in `Layout.astro`
- Try hard refresh: `Ctrl + Shift + R` (or `Cmd + Shift + R` on Mac)

### Issue: Custom domain not working
- Verify DNS records are correct in Cloudflare
- Wait for DNS propagation (can take up to 48 hours)
- Check SSL/TLS settings (should be "Full" or "Full (strict)")

---

## 📚 Next Steps

- **SEO**: Add meta tags for better search engine visibility
- **Analytics**: Consider adding Cloudflare Web Analytics (free)
- **Content**: Add a blog using Astro's content collections
- **Performance**: Astro is already optimized, but you can add image optimization
- **Accessibility**: Test with screen readers and keyboard navigation

---

## 🎉 You're Done!

You now have a professional portfolio that's:
- ✅ Version controlled with Git
- ✅ Hosted on GitHub
- ✅ Deployed on Cloudflare's global CDN
- ✅ Automatically deploys on every push
- ✅ Fast, secure, and professional

Questions? Feel free to reach out!
