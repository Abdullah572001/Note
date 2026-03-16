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

## 🚀 Netlify Deploy Guide

### Step 1 — `netlify.toml` ফাইল তৈরি করো

`public/` folder এর ভেতরে `netlify.toml` নামে একটি ফাইল তৈরি করো এবং নিচের code টুকু লেখো:
```toml
[[redirects]]
from = "/*"
to = "/index.html"
status = 200
```

### Step 2 — File Structure
```
public/
  netlify.toml   ← এখানে রাখো
  index.html
src/
  ...
```

### Step 3 — Build করো
```bash
npm run build
```

### Step 4 — GitHub এ Push করো
```bash
git add .
git commit -m "fix: add netlify.toml for routing"
git push
```

### Step 5 — Netlify Dashboard এ Settings
```
Build command:     npm run build
Publish directory: dist
```

> ⚠️ **এই ফাইলটি ছাড়া** Netlify তে React Router কাজ করবে না এবং page refresh করলে 404 error আসবে।

---

## 🎨 Icons

| Library | Link |
|---|---|
| **Lucide Icons** | [lucide.dev](https://lucide.dev/) |
| **Feather Icons** | [feathericons.com](https://lucide.dev/) |
| **Ionicons** | [ionic.io](https://ionic.io/ionicons) |


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


## 📡 Axios — HTTP Request Library

### Install
```bash
npm install axios
```

---

### Basic Usage
```jsx
import axios from 'axios';
```

---

### All HTTP Methods
```jsx
// GET — data আনো
const res = await axios.get('/api/users');
console.log(res.data);

// POST — data পাঠাও
const res = await axios.post('/api/users', {
  name: "Rahim",
  email: "rahim@gmail.com"
});

// PUT — data update করো
const res = await axios.put('/api/users/1', {
  name: "Karim"
});

// DELETE — data মুছো
const res = await axios.delete('/api/users/1');
```

---

---

> 🔗 Official Docs: [axios-http.com](https://axios-http.com/)


---
> 💡 **Tip:** Bookmark these resources — they will save you hours of development time!
