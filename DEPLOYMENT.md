# Deployment Quick Start Guide

## ✅ Fixed Issues

The GitHub Actions deployment error has been resolved. The issue was:
- The workflow was trying to use `npm ci` and `mintlify build` commands
- Mintlify doesn't use npm dependencies or have a separate build command
- Vercel handles Mintlify builds automatically

## 🚀 Deployment Options

### Option 1: Direct Vercel Deployment (RECOMMENDED - Easiest)

This is the simplest and most reliable method:

1. **Sign in to Vercel:**
   - Go to [vercel.com](https://vercel.com)
   - Sign in with your GitHub account

2. **Import Repository:**
   - Click "Add New Project"
   - Select your `court_strategy` repository
   - Vercel will automatically detect it as a Mintlify site

3. **Deploy:**
   - Click "Deploy" (no configuration needed!)
   - Wait 2-3 minutes for first deploy
   - Your site is live! 🎉

4. **Auto-Deploy on Push:**
   - Every time you push to `main` branch
   - Vercel automatically rebuilds and deploys
   - No GitHub Actions configuration needed

**That's it!** This is the recommended approach.

---

### Option 2: GitHub Actions (Optional - More Control)

If you want GitHub Actions to trigger Vercel deployments:

1. **Deploy via Vercel first** (follow Option 1 above)

2. **Get Vercel Credentials:**
   ```bash
   npm install -g vercel
   cd /Users/nathan.baker/code/court_strategy
   vercel
   ```
   - Follow prompts to link to your Vercel project
   - This creates `.vercel/project.json`

3. **Copy these values from `.vercel/project.json`:**
   - `orgId`
   - `projectId`

4. **Get Vercel Token:**
   - Go to [vercel.com/account/tokens](https://vercel.com/account/tokens)
   - Create new token
   - Copy the token value

5. **Add GitHub Secrets:**
   - Go to your GitHub repo
   - Settings → Secrets and variables → Actions
   - Click "New repository secret" for each:
     - Name: `VERCEL_TOKEN`, Value: (your token)
     - Name: `VERCEL_ORG_ID`, Value: (your orgId)
     - Name: `VERCEL_PROJECT_ID`, Value: (your projectId)

6. **Push to main:**
   ```bash
   git add .
   git commit -m "Setup deployment"
   git push origin main
   ```

Now GitHub Actions will trigger Vercel deployments on every push.

---

## 📝 Before You Commit & Push

### 1. Test Locally

```bash
cd /Users/nathan.baker/code/court_strategy
mintlify dev
```

Visit `http://localhost:3000` and verify:
- ✅ All pages load without errors
- ✅ Navigation works
- ✅ Images appear (or placeholders are acceptable)
- ✅ No broken links

### 2. Verify Files

Make sure these files exist:
```bash
ls -la .github/workflows/deploy.yml   # GitHub Actions (optional)
ls -la mint.json                      # Mintlify config
ls -la vercel.json                    # Vercel config
ls -la README.md                      # Documentation
ls -la .gitignore                     # Ignore rules
```

### 3. Check .gitignore

Ensure these are in `.gitignore`:
- `node_modules/`
- `.mintlify/`
- `client/`
- `notes/` (your private Obsidian notes)

### 4. Initial Commit

```bash
git add .
git commit -m "Initial Mintlify site setup"
git push origin main
```

---

## 🎨 Customization Checklist

After deployment, customize your site:

### Branding
- [ ] Add logo files to `public/images/`:
  - `logo-light.svg`
  - `logo-dark.svg`
  - `favicon.png`
- [ ] Update colors in `mint.json`
- [ ] Replace placeholder email addresses

### Content
- [ ] Add real workshop dates to `/workshops/live-sessions.mdx`
- [ ] Add actual testimonials to `/resources/stories.mdx`
- [ ] Create your 9 video stories
- [ ] Update social media links in `mint.json`

### Analytics
- [ ] Get Google Analytics ID
- [ ] Add to `mint.json` under `analytics.ga4.measurementId`

### Domain
- [ ] Buy domain (e.g., autonateai.com)
- [ ] Add custom domain in Vercel settings
- [ ] Update DNS records

---

## 🔧 Troubleshooting

### Site won't build locally

**Problem:** `mintlify dev` fails

**Solutions:**
1. Reinstall Mintlify: `npm install -g mintlify`
2. Check `mint.json` for JSON syntax errors
3. Verify all referenced files exist
4. Check for typos in file paths

### Vercel deployment fails

**Problem:** Deployment errors in Vercel dashboard

**Solutions:**
1. Check build logs in Vercel
2. Verify `vercel.json` exists
3. Ensure `mint.json` is valid JSON
4. Check that all MDX files have proper frontmatter

### Changes not showing after deploy

**Problem:** Pushed changes but site hasn't updated

**Solutions:**
1. Check Vercel dashboard for deploy status
2. May need to clear browser cache
3. Vercel deployments take 2-3 minutes

### GitHub Actions failing

**Problem:** GitHub Actions workflow errors

**Solutions:**
1. If using direct Vercel integration (Option 1), you can disable GitHub Actions
2. Verify all three secrets are set correctly
3. Check that token hasn't expired

---

## 📚 Next Steps After Deployment

1. **Share your site!** Send the URL to potential workshop participants
2. **Track analytics:** Monitor which pages get the most visits
3. **Iterate on content:** Update based on user feedback
4. **Add real testimonials:** As people complete workshops
5. **Create video stories:** Use your video generator for the 9 stories
6. **Build your community:** Engage with users, answer questions

---

## 🆘 Need Help?

- **Mintlify Docs:** https://mintlify.com/docs
- **Vercel Docs:** https://vercel.com/docs
- **This Project's README:** See `README.md` for detailed info

---

## Summary: What Changed

**Fixed:**
- ❌ Removed `package.json` and `package-lock.json` (not needed)
- ❌ Removed `npm ci` from GitHub Actions
- ❌ Removed `mintlify build` command (doesn't exist)
- ✅ Simplified GitHub Actions to just trigger Vercel
- ✅ Added `vercel.json` for proper Vercel configuration
- ✅ Updated `.gitignore` to exclude Mintlify's internal files
- ✅ Tested local build - works perfectly!

**Your site is ready to deploy!** 🚀

