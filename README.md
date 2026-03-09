# 🚀 Developer Resource Guide

---

## ⚡ Automation Script for Surge Deploy (`package.json`)

Add this script to your `package.json`:
```json
"deploy:surge": "npm run build && cp dist/index.html dist/200.html && surge dist https://your-unique-name.surge.sh"
```

**Run with:**
```bash
npm run deploy:surge
```

---

## 🌐 Deploy with Vercel CLI

**Step 1 — Install Vercel CLI:**
```bash
npm install -g vercel
```

**Step 2 — Deploy:**
```bash
vercel
```

**Step 3 — Final Production Release:**
```bash
vercel --prod
```

**Step 4 — Create `vercel.json` in root folder:**
```json
{
  "rewrites": [
    {
      "source": "/:path*",
      "destination": "/index.html"
    }
  ]
}
```

---

## 🎨 Icons

| Library | Link |
|---|---|
| **Lucide Icons** | [lucide.dev](https://lucide.dev/) |

**Install:**
```bash
npm install lucide-react
```

**Usage:**
```jsx
import { Home, User, Settings } from 'lucide-react';

<Home size={24} color="blue" />
```

---

## 📊 Charts

| Library | Link |
|---|---|
| **Recharts** | [recharts.org](https://recharts.org/) |

**Install:**
```bash
npm install recharts
```

---

## 🧩 Awesome React Components

A curated list of amazing React components and libraries.

🔗 [github.com/brillout/awesome-react-components](https://github.com/brillout/awesome-react-components)

---

> 💡 **Tip:** Bookmark these resources — they will save you hours of development time!
