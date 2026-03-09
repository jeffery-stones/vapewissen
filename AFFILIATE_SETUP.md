# 🤑 Amazon Affiliate Setup Guide

**Status:** Affiliate sections removed (clean content focus first)

**When ready to add back:** Follow this guide after Amazon Associates approval.

---

## Step 1: Apply for Amazon Associates

1. **Register domain first:** `vapewissen.de` must be live
2. **Go to:** [partnernet.amazon.de](https://partnernet.amazon.de)
3. **Sign up:**
   - Website: `https://vapewissen.de`
   - Content description: "Cannabis science blog & vaporizer reviews in German"
4. **Wait for approval:** Usually 1-3 days
5. **Get your Associate Tag:** e.g., `vapewissen-21`

---

## Step 2: Add Product Sections Back

### In Article Frontmatter

Add this to `.md` files (e.g., `content/artikel/temperatur-guide.md`):

```yaml
---
title: "Your Title"
# ... other fields ...
products:
  - name: "Storz & Bickel Mighty+"
    description: "Der beste portable Vaporizer 2026. Präzise Temperaturkontrolle, 2 Stunden Akku."
    price: "349€"
    link: "https://www.amazon.de/dp/B09FXR9Z4P?tag=YOUR_TAG_HERE"
  - name: "Volcano Hybrid"
    description: "Der Klassiker für Zuhause. Ballon- und Schlauchsystem, unverwüstlich."
    price: "699€"
    link: "https://www.amazon.de/dp/B07VFHX6YD?tag=YOUR_TAG_HERE"
---
```

**Replace `YOUR_TAG_HERE` with your actual Amazon Associate Tag!**

---

## Step 3: Update Templates

### Re-enable products display in `layouts/_default/single.html`

Add this after `{{ .Content }}`:

```html
{{ with .Params.products }}
<div class="products-section">
    <h2>🔥 Empfohlene Vaporizer</h2>
    {{ range . }}
    <div class="product-card">
        <h3>{{ .name }}</h3>
        <p>{{ .description }}</p>
        <p class="price"><strong>Preis: {{ .price }}</strong></p>
        <a href="{{ .link }}" class="btn" target="_blank" rel="noopener">
            Bei Amazon ansehen →
        </a>
    </div>
    {{ end }}
</div>
{{ end }}
```

---

## Step 4: Add Products to Homepage (Optional)

Edit `layouts/index.html`, add before `<section class="quick-tips">`:

```html
<section class="products-section">
    <h2>🔥 Top Vaporizer 2026</h2>
    
    <div class="product-card">
        <h3>Storz & Bickel Mighty+</h3>
        <p><strong>Best Overall</strong> - Der beste portable Vaporizer 2026.</p>
        <p class="price">349€</p>
        <a href="https://www.amazon.de/dp/B09FXR9Z4P?tag=YOUR_TAG" class="btn">
            Bei Amazon ansehen →
        </a>
    </div>

    <div class="product-card">
        <h3>Volcano Hybrid</h3>
        <p><strong>Best Desktop</strong> - Der Klassiker für Zuhause.</p>
        <p class="price">699€</p>
        <a href="https://www.amazon.de/dp/B07VFHX6YD?tag=YOUR_TAG" class="btn">
            Bei Amazon ansehen →
        </a>
    </div>

    <div class="product-card">
        <h3>DynaVap "M" Plus</h3>
        <p><strong>Best Budget</strong> - Perfekt für Einsteiger.</p>
        <p class="price">75€</p>
        <a href="https://www.amazon.de/dp/B0BLQH7X8F?tag=YOUR_TAG" class="btn">
            Bei Amazon ansehen →
        </a>
    </div>
</section>
```

---

## Step 5: Add Affiliate Disclaimer to Footer

Edit `layouts/_default/baseof.html`, add after first `<p>` in footer:

```html
<p class="disclaimer">
    Affiliate-Links: Wir erhalten eine Provision bei Käufen über unsere Links. Keine Mehrkosten für dich.
</p>
```

---

## Step 6: Test & Deploy

```bash
cd /home/node/.openclaw/workspace/vapewissen

# Test locally
hugo server
# Visit http://localhost:1313 and check links

# Build & deploy
hugo --minify
git add -A
git commit -m "Add Amazon affiliate links"
git push

# Netlify auto-deploys in 30 seconds
```

---

## Product Links Reference

### Vaporizers (Amazon.de)

**Portable:**
- Mighty+: `https://www.amazon.de/dp/B09FXR9Z4P`
- Crafty+: `https://www.amazon.de/dp/B07VF7RYQK`
- PAX 3: `https://www.amazon.de/dp/B06XCN9KPC`
- DynaVap M Plus: `https://www.amazon.de/dp/B0BLQH7X8F`

**Desktop:**
- Volcano Hybrid: `https://www.amazon.de/dp/B07VFHX6YD`
- Volcano Classic: `https://www.amazon.de/dp/B00B8JI9TW`
- Arizer Extreme Q: `https://www.amazon.de/dp/B00JDL6C2C`

**Budget:**
- XMAX V3 Pro: `https://www.amazon.de/dp/B09JFKQY8L`
- Flowermate Slick: `https://www.amazon.de/dp/B08D3QN8M9`

**Always append:** `?tag=YOUR_ASSOCIATE_TAG`

**Example:** `https://www.amazon.de/dp/B09FXR9Z4P?tag=vapewissen-21`

---

## Commission Rates (Amazon.de)

- **Electronics:** 3%
- **Home & Kitchen:** 5-8%

**Most vaporizers = 3-5% commission**

### Revenue Examples:
- Mighty+ (€349) @ 5% = **€17.45** per sale
- Volcano (€699) @ 5% = **€34.95** per sale
- DynaVap (€75) @ 5% = **€3.75** per sale

---

## Amazon Associates Requirements

### To Stay Active:
- **3 sales within 180 days** of approval
- If no sales in 180 days → account closed
- Need to re-apply

### Best Practices:
1. **Full disclosure:** Always mention affiliate relationship
2. **Quality over quantity:** Review products honestly
3. **Track performance:** Use Amazon's dashboard
4. **Diversify:** Don't rely only on Amazon (consider other affiliate programs)

---

## Alternative Affiliate Programs

If Amazon doesn't work out or for diversification:

1. **AWIN** (Affiliate Window)
   - German vaporizer shops
   - Often higher commissions (10-15%)

2. **Digistore24**
   - Digital products
   - Cannabis education courses

3. **Direct partnerships**
   - Email vaporizer manufacturers
   - Request affiliate programs
   - Often best rates (15-20%)

---

## Tracking Affiliate Performance

### In Amazon Associates Dashboard:

Monitor:
- **Clicks:** How many people clicked your links
- **Conversion rate:** % of clicks that buy
- **Earnings:** Total commission
- **Best sellers:** Which products convert best

**Target metrics:**
- Click-through rate: 3-5%
- Conversion rate: 2-5%
- Revenue per 1000 visitors: €20-50

---

## When to Add Affiliates

**Good timing:**
- ✅ Site has 500+ monthly visitors
- ✅ Amazon Associates approved
- ✅ 10+ quality articles published
- ✅ Established reader trust

**Too early:**
- ❌ Site brand new (no traffic yet)
- ❌ Only 2-3 articles
- ❌ Not yet approved by Amazon

**Current status:** Focus on content first, add affiliates when traffic is growing!

---

## Quick Re-Enable Checklist

When ready to add back:

- [ ] Amazon Associates approved
- [ ] Got your Associate Tag
- [ ] Update article frontmatter (add `products:`)
- [ ] Update `layouts/_default/single.html` template
- [ ] Add products to homepage (optional)
- [ ] Add disclaimer to footer
- [ ] Replace all `YOUR_TAG` with actual tag
- [ ] Test links in incognito window
- [ ] Commit & deploy
- [ ] Verify links work on live site

---

**Current site is clean and focused on content. Add affiliates when the time is right!** 🚀
