# Chemistry Cards — IITians Curious Minds

> Website for displaying chemistry question cards with QR codes linking to answers.
> To be hosted at: **cards.iitianscuriousminds.com**

---

## 📁 Project Structure

```
chemistry-cards-site/
├── vercel.json          ← Vercel config (rewrites + output dir)
└── public/
    ├── index.html       ← Main page (all 39 question cards + QR codes)
    ├── answer.html      ← Answer page (reads card ID from URL)
    ├── cards/
    │   ├── 1.jpg        ← Question card images (1–39)
    │   └── ...
    └── answers/
        ├── 1.jpg        ← Answer images (1–39)
        └── ...
```

---

## 🚀 Deploying to Vercel (Step by Step)

### Step 1 — Install Vercel CLI (if not done)
```bash
npm install -g vercel
```

### Step 2 — Login to Vercel
```bash
vercel login
```

### Step 3 — Deploy from project folder
```bash
cd chemistry-cards-site
vercel --prod
```
Vercel will give you a URL like `your-project.vercel.app`.

### Step 4 — Add Custom Domain on Vercel Dashboard
1. Go to **vercel.com** → your project → **Settings** → **Domains**
2. Add domain: `cards.iitianscuriousminds.com`
3. Vercel will show you a **CNAME record** to add

### Step 5 — Update DNS at your domain registrar
Add this CNAME in your DNS settings:
- **Type**: CNAME
- **Name**: `cards`
- **Value**: `cname.vercel-dns.com`

Wait 5–15 minutes for DNS to propagate. Done! ✅

---

## 🔗 How URLs Work

| URL | What it does |
|-----|-------------|
| `cards.iitianscuriousminds.com/` | Shows all 39 question cards |
| `cards.iitianscuriousminds.com/answer/1` | Shows answer for card 1 |
| `cards.iitianscuriousminds.com/answer/15` | Shows answer for card 15 |

---

## 📱 QR Codes — Important!

The QR codes on the **website** are generated **automatically** using the current domain.

- During local testing → QR codes point to `localhost`
- After deploying to `cards.iitianscuriousminds.com` → QR codes automatically point to that domain

**Print the QR codes from the deployed website** to use on physical cards.

---

## ✏️ Customization

### Add/remove cards
Edit the `TOTAL_CARDS` variable in `public/index.html`:
```js
const TOTAL_CARDS = 39; // change this number
```

### Change colors
Edit CSS variables at the top of any HTML file:
```css
:root {
  --accent: #e05444;   /* red accent color */
  --bg: #0f0f0f;       /* background */
}
```

---

## 📋 Card → Answer Mapping

| Question Card | Answer Image |
|---|---|
| `public/cards/1.jpg` | `public/answers/1.jpg` |
| `public/cards/2.jpg` | `public/answers/2.jpg` |
| ... | ... |
| `public/cards/39.jpg` | `public/answers/39.jpg` |

Original PDF: questions on pages 1–40, answers on pages 42–80 (page 41 = branding).
