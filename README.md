# StockHunter Pro — מדריך הפצה מלא

## מה יש בתיקייה
- `index.html` — דף הנחיתה (landing page)
- `app.html` — הסקרינר המלא (לאחר התחברות)

---

## שלב 1 — העלה ל-GitHub Pages (חינם, 10 דקות)

1. כנס ל-https://github.com ו**צור חשבון חינם**
2. לחץ "New repository"
3. שם: `stockhunter-pro` | סמן **Public** | לחץ Create
4. לחץ "uploading an existing file"
5. גרור את `index.html` ו-`app.html`
6. לחץ "Commit changes"
7. עבור ל-Settings → Pages → Source: **main** / root → Save
8. האתר יהיה חי ב: `https://YOUR-USERNAME.github.io/stockhunter-pro`

---

## שלב 2 — חבר דומיין

לאחר שתקנה דומיין (Namecheap / GoDaddy):
1. ב-GitHub Pages Settings → Custom domain → הכנס את הדומיין שלך
2. אצל ספק הדומיין — הוסף CNAME record:
   - Name: `www`
   - Value: `YOUR-USERNAME.github.io`

---

## שלב 3 — הגדר Stripe לתשלומים

1. פתח חשבון ב-https://stripe.com (חינם)
2. עבור ל-Products → Add Product
   - שם: "StockHunter Pro"
   - מחיר: $9 / month / recurring
3. עבור ל-Payment Links → Create payment link
4. **העתק את ה-URL** (נראה כך: `https://buy.stripe.com/xxxx`)
5. ב-`index.html`, מצא את השורה:
   ```
   // window.open('https://buy.stripe.com/YOUR_LINK', '_blank');
   ```
   והחלף ל:
   ```
   window.open('https://buy.stripe.com/YOUR_ACTUAL_LINK', '_blank');
   ```

---

## שלב 4 — אסוף אימיילים (אופציונלי, ממליץ)

לפני Stripe — אסוף אימיילים עם Mailchimp/ConvertKit (שניהם חינמיים עד 500 איש).

ב-`index.html` בפונקציה `handleSignup()`, הוסף:
```javascript
// Mailchimp API (free tier)
fetch('https://YOUR-MAILCHIMP-ENDPOINT', {
  method: 'POST',
  body: JSON.stringify({ email_address: email, status: 'subscribed' })
});
```

---

## עלויות חודשיות

| שירות | עלות |
|-------|------|
| GitHub Pages | $0 |
| Stripe | 2.9% + $0.30 לעסקה |
| Anthropic API (AI) | ~$0.01 לניתוח |
| דומיין | ~$12/שנה |
| **סה"כ** | **$12/שנה + עמלות Stripe** |

---

## הכנסות פוטנציאליות

| משתמשים | הכנסה חודשית | אחרי Stripe (~3%) |
|---------|-------------|-------------------|
| 10 | $90 | ~$87 |
| 50 | $450 | ~$436 |
| 100 | $900 | ~$873 |
| 500 | $4,500 | ~$4,365 |

---

## הצעדים הבאים לצמיחה

1. **SEO** — הוסף meta tags, schema markup, blog עם תוכן על value investing
2. **Product Hunt** — פרסם שם לחשיפה ראשונה
3. **Reddit** — r/investing, r/stocks, r/ValueInvesting
4. **Twitter/X** — פרסם סיגנלים יומיים עם mention של @StockHunterPro
5. **נתונים אמיתיים** — כשיהיו 50+ משלמים, השקע ב-Yahoo Finance API ($25/חודש)
