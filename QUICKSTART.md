# ⚡ Quick Start - 5 Minutes to Live

## 🎯 Goal

Get VapeWissen.de live on the internet in 5 minutes.

---

## 📋 What You Need

1. **GitHub account** (create at github.com - 30 seconds)
2. **Netlify account** (sign up with GitHub - 10 seconds)
3. That's it!

*Domain can come later*

---

## 🚀 Steps

### 1. Create GitHub Repo (2 min)

```bash
# You're already in the project
cd /home/node/.openclaw/workspace/vapewissen

# Create repo at github.com/new
# Name it: vapewissen
# Don't initialize with README (we already have one)

# Then push:
git remote add origin https://github.com/YOUR_USERNAME/vapewissen.git
git push -u origin main
```

**Can't push?** You need a Personal Access Token:
- Go to github.com/settings/tokens
- Generate new token (classic)
- Select: `repo` scope
- Use token as password when pushing

---

### 2. Deploy on Netlify (2 min)

1. Go to [app.netlify.com](https://app.netlify.com)
2. Click **"New site from Git"**
3. Choose **GitHub** → Select `vapewissen` repo
4. Build settings auto-detected (from `netlify.toml`)
5. Click **"Deploy"**
6. Wait 30 seconds
7. **Your site is LIVE!** 🎉

Netlify gives you a URL like: `https://random-name-12345.netlify.app`

---

### 3. Test It (30 sec)

Open your Netlify URL. You should see:
- ✅ Homepage with "VapeWissen.de"
- ✅ Two articles (Temperatur, Cannabinoide)
- ✅ Product cards (Mighty+, Volcano, DynaVap)
- ✅ Mobile-responsive design

---

### 4. Add New Article (1 min)

```bash
# Create new article
hugo new content/artikel/test-artikel.md

# Edit it
nano content/artikel/test-artikel.md

# Commit & push
git add .
git commit -m "Add test article"
git push

# Netlify auto-deploys in 30 seconds
# Refresh your site → new article appears!
```

---

## 🌐 Custom Domain (Optional, Later)

When ready:
1. Register `vapewissen.de` at Namecheap (~€12/year)
2. Netlify → Domain settings → Add domain
3. Update nameservers in Namecheap
4. Wait 5-60 min → Done!

Full instructions: See `DEPLOY.md`

---

## 🤑 Amazon Associates (Later)

1. Domain needs to be live first
2. Apply at partnernet.amazon.de
3. Get your tag (e.g., `vapewissen-21`)
4. Replace placeholder tag in articles
5. Start earning!

---

## 🎨 Customize

### Change Colors

Edit `static/css/style.css`:
```css
:root {
    --green: #2ecc71;  /* Change this */
    --bg: #0a0a0a;     /* Or this */
}
```

### Change Logo

Edit `layouts/_default/baseof.html`:
```html
<a href="/" class="logo">🌿 VapeWissen.de</a>
<!-- Change emoji or text -->
```

### Add More Content

```bash
hugo new content/artikel/your-article.md
# Edit, commit, push → Auto-deploys
```

---

## 📊 Track Traffic (Optional)

Add Google Analytics:
1. Create property at analytics.google.com
2. Copy tracking code
3. Add to `layouts/_default/baseof.html` in `<head>`
4. Commit & push

---

## ✅ You're Done!

**Live site in 5 minutes. No domain required.**

Domain, Amazon, SEO → can all come later.

**Right now:** You have a real website publishing content!

---

## 🆘 Help

- **Build failing?** Check Netlify logs
- **Can't push to GitHub?** Need Personal Access Token
- **Design looks broken?** Clear browser cache (Ctrl+Shift+R)

Full deployment guide: `DEPLOY.md`  
Full docs: `README.md`
