# 🚀 Deployment Guide

## Prerequisites

1. **Domain:** Register `vapewissen.de` at [Namecheap](https://namecheap.com) (~€12/year)
2. **GitHub Account:** Create at [github.com](https://github.com) (free)
3. **Netlify Account:** Sign up at [netlify.com](https://netlify.com) (free)

---

## Step 1: Push to GitHub

### Option A: If you have GitHub access token

```bash
cd /home/node/.openclaw/workspace/vapewissen

# Add remote (replace with your token & username)
git remote add origin https://YOUR_TOKEN@github.com/YOUR_USERNAME/vapewissen.git

# Push
git push -u origin main
```

### Option B: If you need to create repo manually

1. Go to [github.com/new](https://github.com/new)
2. Create repo named `vapewissen`
3. Copy the HTTPS URL
4. Run:
   ```bash
   cd /home/node/.openclaw/workspace/vapewissen
   git remote add origin https://github.com/YOUR_USERNAME/vapewissen.git
   git push -u origin main
   ```

---

## Step 2: Deploy on Netlify

### Automatic Deploy (Recommended)

1. Go to [app.netlify.com](https://app.netlify.com)
2. Click **"New site from Git"**
3. Choose **GitHub**
4. Select your `vapewissen` repo
5. **Build settings:**
   - Build command: `hugo --minify`
   - Publish directory: `public`
   - Hugo version: `0.138.0` (auto-detected from netlify.toml)
6. Click **"Deploy site"**
7. Wait ~1 minute → Site is live!

### Manual Deploy (No GitHub)

1. Build locally:
   ```bash
   cd /home/node/.openclaw/workspace/vapewissen
   hugo --minify
   ```

2. Go to [app.netlify.com/drop](https://app.netlify.com/drop)

3. Drag the `public/` folder onto the page

4. Done! (But no auto-updates)

---

## Step 3: Connect Custom Domain

1. **In Netlify Dashboard:**
   - Site settings → Domain management
   - Click **"Add custom domain"**
   - Enter `vapewissen.de`
   - Click **"Verify"**

2. **Copy Netlify DNS servers** (shown in Netlify)
   - Usually: `dns1.p03.nsone.net`, `dns2.p03.nsone.net`, etc.

3. **In Namecheap:**
   - Log in → Domain List → Manage `vapewissen.de`
   - Nameservers → Select **"Custom DNS"**
   - Paste Netlify's DNS servers
   - Save changes

4. **Wait 5-60 minutes** for DNS propagation

5. **Enable HTTPS** (automatic in Netlify after DNS propagates)

---

## Step 4: Amazon Associates

1. Go to [partnernet.amazon.de](https://partnernet.amazon.de)

2. Sign up:
   - Website: `https://vapewissen.de`
   - Describe content: "Cannabis science blog & vaporizer reviews"

3. Get approved (usually 1-3 days)

4. Get your **Associate Tag** (e.g., `vapewissen-21`)

5. **Update all affiliate links** in articles:
   - Find: `?tag=vapewissen-21`
   - Replace with your actual tag
   - Commit & push (Netlify auto-deploys)

---

## Step 5: Submit Sitemap to Google

**✅ Google Search Console already set up!** (TXT record verified)

Now submit your sitemap:

1. Go to [search.google.com/search-console](https://search.google.com/search-console)
2. Select property: `vapewissen.de`
3. Click **Sitemaps** in left menu
4. Add new sitemap: `https://vapewissen.de/sitemap.xml`
5. Click **Submit**

**Request indexing for key pages:**
- In Search Console → **URL Inspection**
- Enter URL → Click **"Request Indexing"**
- Do this for:
  - `https://vapewissen.de/`
  - `https://vapewissen.de/artikel/temperatur-guide/`
  - `https://vapewissen.de/artikel/cannabinoide-guide/`

**Google Analytics** (optional):
- Create property at [analytics.google.com](https://analytics.google.com)
- Add tracking code to `layouts/_default/baseof.html`

**Full SEO checklist:** See `SEO_CHECKLIST.md`

---

## Ongoing Updates

### Add New Article

```bash
# Create new article
hugo new content/artikel/neuer-artikel.md

# Edit the MD file
nano content/artikel/neuer-artikel.md

# Commit & push
git add .
git commit -m "Add neuer-artikel"
git push

# Netlify auto-deploys in ~30 seconds
```

### Update Existing Article

```bash
# Edit MD file
nano content/artikel/temperatur-guide.md

# Commit & push
git add .
git commit -m "Update temperatur-guide"
git push
```

---

## Troubleshooting

### Site not building on Netlify?

- Check build logs in Netlify dashboard
- Ensure Hugo version matches (0.138.0)
- Verify `netlify.toml` exists

### Domain not working?

- Check DNS propagation: [whatsmydns.net](https://whatsmydns.net)
- Wait up to 24 hours (usually 5-60 min)
- Verify nameservers in Namecheap match Netlify

### Affiliate links not working?

- Ensure you've replaced `vapewissen-21` with YOUR tag
- Check link format: `https://www.amazon.de/dp/PRODUCT_ID?tag=YOUR_TAG`
- Amazon requires 3 sales within 180 days to stay active

---

## Success Checklist

- [ ] Domain registered (vapewissen.de)
- [ ] Code pushed to GitHub
- [ ] Site deployed on Netlify
- [ ] Custom domain connected
- [ ] HTTPS enabled
- [ ] Amazon Associates approved
- [ ] Affiliate links updated
- [ ] Google Search Console submitted
- [ ] First article published
- [ ] Shared on Reddit/social

---

**You're live! 🎉**

Next: Write more articles, promote on social media, earn that first €100!
