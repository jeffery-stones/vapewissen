# 📬 ConvertKit Setup

⚠️ **Credentials stored in:** `CREDENTIALS.md` (gitignored - not committed to repo)

**Login URL:** https://app.convertkit.com

---

## Step 1: Get Your Form ID

1. Log in to [app.convertkit.com](https://app.convertkit.com)
2. Go to **Grow** → **Landing Pages & Forms**
3. Create a new form (or use existing)
4. Click **Share** → **Embed**
5. Copy the **Form ID** (looks like: `1234567`)

---

## Step 2: Update Newsletter Form

### Option A: ConvertKit Embed (Recommended)

Edit `layouts/index.html`, replace the current form section:

```html
<section class="newsletter">
    <h3>📬 Wöchentliche Cannabis-Wissenschaft</h3>
    <p>Neue Guides, Vaporizer-Tests und Deals direkt in dein Postfach.</p>
    
    <!-- ConvertKit Form -->
    <script async data-uid="YOUR_FORM_ID" src="https://vapewissen-team.ck.page/YOUR_FORM_ID/index.js"></script>
</section>
```

**Replace `YOUR_FORM_ID` with your actual Form ID!**

---

### Option B: API Integration (Advanced)

If you want custom styling, use ConvertKit API:

```html
<section class="newsletter">
    <h3>📬 Wöchentliche Cannabis-Wissenschaft</h3>
    <p>Neue Guides, Vaporizer-Tests und Deals direkt in dein Postfach.</p>
    
    <form id="newsletter-form">
        <input type="email" id="email" placeholder="deine@email.de" required>
        <button type="submit" class="btn">Anmelden →</button>
    </form>
    <p id="form-message" style="display:none; margin-top: 1rem;"></p>
</section>

<script>
document.getElementById('newsletter-form').addEventListener('submit', async (e) => {
    e.preventDefault();
    const email = document.getElementById('email').value;
    const message = document.getElementById('form-message');
    
    try {
        const response = await fetch('https://api.convertkit.com/v3/forms/YOUR_FORM_ID/subscribe', {
            method: 'POST',
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify({
                api_key: 'YOUR_API_KEY',
                email: email
            })
        });
        
        if (response.ok) {
            message.style.display = 'block';
            message.style.color = '#2ecc71';
            message.textContent = '✅ Erfolgreich angemeldet! Check deine E-Mails.';
            document.getElementById('email').value = '';
        } else {
            throw new Error('Subscription failed');
        }
    } catch (error) {
        message.style.display = 'block';
        message.style.color = '#e74c3c';
        message.textContent = '❌ Fehler. Bitte versuche es erneut.';
    }
});
</script>
```

---

## Step 3: Get API Key (for Option B)

1. In ConvertKit → **Settings** → **Advanced**
2. Copy **API Key**
3. Replace `YOUR_API_KEY` in the script above

---

## Step 4: Style the Form (Optional)

If using embedded ConvertKit form, you can customize via CSS:

```css
/* Add to static/css/style.css */

.newsletter .formkit-form {
    max-width: 400px !important;
    margin: 0 auto !important;
}

.newsletter .formkit-input {
    width: 100% !important;
    padding: var(--spacing-sm) !important;
    font-size: 1rem !important;
    border: 1px solid rgba(255,255,255,0.2) !important;
    background: var(--bg) !important;
    color: var(--text) !important;
    border-radius: 4px !important;
    margin-bottom: var(--spacing-sm) !important;
}

.newsletter .formkit-submit {
    width: 100% !important;
    padding: var(--spacing-sm) var(--spacing-lg) !important;
    background: var(--green) !important;
    color: white !important;
    border: none !important;
    border-radius: 4px !important;
    font-weight: bold !important;
    cursor: pointer !important;
}
```

---

## Step 5: Set Up Email Sequence (Optional)

In ConvertKit, create an automated email sequence:

### Email 1: Welcome (Immediate)
**Subject:** "Willkommen bei VapeWissen! 🌿"

```
Hey [First Name],

Willkommen bei VapeWissen!

Du bekommst jetzt wöchentlich:
- Neue Cannabis-Wissenschaft Guides
- Vaporizer Tests & Reviews
- Tipps für optimale Temperatur & Dosierung

Zum Start: Unser beliebtester Guide →
[Link to Temperatur Guide]

Bis nächste Woche!
VapeWissen Team
```

### Email 2: Best Articles (3 days later)
**Subject:** "Die 3 wichtigsten Vaporizer-Tipps"

Share your top 3 articles.

### Email 3: Ask for Feedback (7 days later)
**Subject:** "Welches Thema interessiert dich?"

Ask subscribers what they want to learn about.

---

## Step 6: GDPR Compliance (Germany)

ConvertKit is GDPR-compliant, but make sure:

1. **Double opt-in enabled** (Settings → Forms → Require confirmation)
2. **Privacy policy link** in form
3. **Unsubscribe link** in every email (ConvertKit adds this automatically)

---

## Step 7: Track Performance

Monitor in ConvertKit dashboard:
- **Subscribers:** Total email list size
- **Growth rate:** New subscribers per week
- **Open rate:** % who open emails (aim for 30-50%)
- **Click rate:** % who click links (aim for 3-10%)

---

## Integration Checklist

- [ ] Log in to ConvertKit
- [ ] Create signup form
- [ ] Get Form ID
- [ ] Update `layouts/index.html` with embed code
- [ ] Test signup on local site
- [ ] Enable double opt-in
- [ ] Create welcome email sequence
- [ ] Add privacy policy link (if not already)
- [ ] Commit & deploy
- [ ] Test signup on live site

---

## Quick Start (Easiest Path)

1. Log in to ConvertKit
2. Create a form
3. Get the embed code
4. Replace current `<form>` in `layouts/index.html` with embed
5. Done!

**ConvertKit handles everything:** Email delivery, unsubscribes, GDPR, analytics.

---

## Alternative: Mailchimp

If you prefer Mailchimp instead:

1. Create list at [mailchimp.com](https://mailchimp.com)
2. Get embedded form code
3. Similar integration as ConvertKit

**Recommendation:** Stick with ConvertKit - cleaner, better for creators.

---

Need help with integration? Let me know your Form ID and I'll update the template for you!
