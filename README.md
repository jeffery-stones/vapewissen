# 🌿 VapeWissen.de

**Wissenschaftlich fundierte Cannabis Guides & Vaporizer Reviews**

Modern, mobile-first blog built with Hugo. Content lives in Markdown files.

---

## 🚀 Quick Start

### Local Development

```bash
# Install Hugo (if not installed)
# macOS: brew install hugo
# Linux: wget https://github.com/gohugoio/hugo/releases/download/v0.138.0/hugo_extended_0.138.0_Linux-64bit.tar.gz
# Windows: choco install hugo-extended

# Run dev server
hugo server -D

# Build production site
hugo --minify
```

Site runs at `http://localhost:1313`

---

## 📝 Adding Content

### Create New Article

```bash
hugo new content/artikel/dein-artikel.md
```

### Article Template

```yaml
---
title: "Dein Titel"
description: "SEO Description"
date: 2026-03-09
readingtime: "8 Minuten"
author: "VapeWissen Team"
products:
  - name: "Product Name"
    description: "Short desc"
    price: "99€"
    link: "https://amazon.de/..."
---

## Dein Content in Markdown

- Bullet lists
- **Bold text**
- [Links](https://example.com)

### Subsections

Tables, code blocks, everything Markdown supports.
```

Just edit Markdown files in `content/artikel/` and rebuild!

---

## 🎨 Design

- **Mobile-first** responsive design
- **Dark theme** optimized for readability
- **Touch-friendly** (44x44px tap targets)
- **Fast** (static HTML, no JS)
- **SEO-optimized** (semantic HTML, meta tags)

---

## 📂 Project Structure

```
vapewissen/
├── content/
│   └── artikel/              # Markdown articles go here
│       ├── temperatur-guide.md
│       └── cannabinoide-guide.md
├── layouts/
│   ├── _default/
│   │   ├── baseof.html       # Base template
│   │   └── single.html       # Article template
│   └── index.html            # Homepage template
├── static/
│   └── css/
│       └── style.css         # Mobile-first CSS
├── hugo.toml                 # Site config
└── public/                   # Generated site (deploy this)
```

---

## 🚢 Deployment

### Option 1: Netlify (Recommended)

1. **Push to GitHub:**
   ```bash
   # Create repo at github.com
   git remote add origin https://github.com/yourusername/vapewissen.git
   git push -u origin main
   ```

2. **Connect to Netlify:**
   - Go to [netlify.com](https://netlify.com)
   - "New site from Git"
   - Select your repo
   - Build command: `hugo --minify`
   - Publish directory: `public`
   - Deploy!

3. **Custom Domain:**
   - Netlify Dashboard → Domain settings
   - Add `vapewissen.de`
   - Update DNS at Namecheap

### Option 2: Netlify Drop (No GitHub)

1. Build the site:
   ```bash
   hugo --minify
   ```

2. Go to [app.netlify.com/drop](https://app.netlify.com/drop)

3. Drag `public/` folder

4. Done! Site is live.

### Option 3: Vercel

Same as Netlify, but use [vercel.com](https://vercel.com)

---

## 🔗 Amazon Associates Setup

1. **Register Domain:** `vapewissen.de` at Namecheap (€12/year)

2. **Apply for Amazon Associates:**
   - Go to [partnernet.amazon.de](https://partnernet.amazon.de)
   - Sign up with `vapewissen.de` as website
   - Get your Associate Tag (e.g., `vapewissen-21`)

3. **Update Links:**
   - Find all `?tag=vapewissen-21` links in MD files
   - Replace with your actual Associate Tag

4. **Start Earning:**
   - 3-8% commission on sales
   - Mighty+ (€349): €17.45/sale
   - Volcano (€699): €34.95/sale

---

## 📈 SEO & Growth

### Current Articles

1. **Cannabis Temperatur Guide** - Target: "cannabis temperatur" (3.6k/mo)
2. **Cannabinoide Guide** - Target: "cannabinoide wirkung" (1.2k/mo)

### Next Articles to Write

- **Terpene Guide** - "cannabis terpene" (2.1k/mo)
- **AVB verwerten** - "avb cannabis" (800/mo)
- **Vaporizer Test 2026** - "vaporizer test" (5k/mo)
- **Mighty+ Review** - "mighty+ test" (1.2k/mo)
- **Anfänger Guide** - "vaporizer anfänger" (900/mo)

### Promotion Channels

- **Reddit:** r/vaporents, r/germantrees
- **Pinterest:** Create pins from guide sections
- **Instagram:** @vapewissen
- **Google Search Console:** Submit sitemap

---

## 💰 Revenue Model

**Month 1:** 500 visitors, 1-2 sales, €50  
**Month 3:** 3,000 visitors, 5-10 sales, €200  
**Month 6:** 10,000 visitors, 20-30 sales, €800  
**Month 12:** 30,000 visitors, 60-100 sales, €2,500

**Year 2:** €3k-10k/month passive income

---

## 🛠️ Maintenance

### Adding New Article

1. Create MD file: `hugo new content/artikel/artikel-name.md`
2. Write content in Markdown
3. Build: `hugo --minify`
4. Commit & push to GitHub (Netlify auto-deploys)

### Updating Existing Article

1. Edit MD file in `content/artikel/`
2. Rebuild & deploy

### Changing Design

1. Edit `static/css/style.css`
2. Rebuild & deploy

---

## 📦 Tech Stack

- **Hugo** (v0.138.0) - Static site generator
- **Markdown** - Content format
- **CSS** - Mobile-first design (no frameworks)
- **Netlify** - Hosting (free tier)
- **Amazon Associates** - Monetization

---

## 🤝 Contributing

This is your project. Add more articles, improve design, experiment!

**Quick wins:**
- Add more vaporizer reviews
- Create comparison tables
- Build email list (ConvertKit)
- Add FAQ sections
- Create video content

---

## 📄 License

Content: All rights reserved  
Code: MIT License

---

**Built with ❤️ for the German cannabis community**

Questions? jeff@dercio.de
