# 🚀 Quick Deploy Guide

## TL;DR - Fastest Way to Deploy

**Just use Vercel's native GitHub integration. No configuration needed!**

### Step 1: Connect to Vercel (2 minutes)

1. Go to **[vercel.com](https://vercel.com)** and sign in with GitHub
2. Click **"Add New Project"**
3. Select your **`court_strategy`** repository
4. Click **"Deploy"** (don't change any settings!)
5. Wait 2-3 minutes... ✨ **Your site is live!**

### Step 2: That's It!

Every time you push to `main` branch, Vercel automatically redeploys your site. No GitHub Actions, no secrets, no configuration needed.

---

## ❓ FAQ

**Q: Do I need to set up GitHub Actions?**  
**A:** No! The `.github/workflows/deploy.yml` file is commented out (disabled). Vercel handles deployment automatically.

**Q: What about those Vercel secrets (VERCEL_TOKEN, etc.)?**  
**A:** Not needed for Vercel's native integration. Only needed if you enable GitHub Actions (optional).

**Q: How do I know it's deployed?**  
**A:** After connecting in Vercel, you'll get a URL like `https://court-strategy.vercel.app`

**Q: Can I use a custom domain?**  
**A:** Yes! In Vercel dashboard → Settings → Domains → Add your domain

---

## 📝 Testing Before Deploy

```bash
cd /Users/nathan.baker/code/court_strategy
mintlify dev
```

Visit `http://localhost:3000` to preview locally.

---

## 🎨 Next Steps After Deployment

1. **Add your logo:** Put `logo-light.svg`, `logo-dark.svg`, and `favicon.png` in `public/images/`
2. **Update colors:** Edit `mint.json` to change theme colors
3. **Add analytics:** Get Google Analytics ID and add to `mint.json`
4. **Custom domain:** Add your domain in Vercel settings
5. **Update content:** Replace placeholder emails and social links

---

## 🔧 Optional: Enable GitHub Actions

Only do this if you want GitHub Actions to trigger Vercel (most people don't need this):

1. Uncomment the workflow in `.github/workflows/deploy.yml`
2. Follow detailed instructions in `DEPLOYMENT.md`
3. Set up GitHub secrets

**Most users should skip this - Vercel's native integration is better!**

---

## 🆘 Problems?

**Site won't build locally?**
- Reinstall: `npm install -g mintlify`
- Check for JSON syntax errors in `mint.json`

**Vercel deployment failed?**
- Check build logs in Vercel dashboard
- Verify `mint.json` is valid JSON
- Make sure all MDX files have frontmatter

**Changes not appearing?**
- Check Vercel dashboard for deploy status
- Deployments take 2-3 minutes
- Clear browser cache

---

**Your site is ready to deploy! Just connect to Vercel and go! 🚀**

