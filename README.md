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

### React এ useEffect দিয়ে ব্যবহার
```jsx
import axios from 'axios';
import { useEffect, useState } from 'react';

function UserList() {
  const [users, setUsers] = useState([]);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    axios.get('https://jsonplaceholder.typicode.com/users')
      .then(res => setUsers(res.data))
      .catch(err => setError(err.message))
      .finally(() => setLoading(false));
  }, []);

  if (loading) return <p>Loading...</p>;
  if (error) return <p>Error: {error}</p>;

  return (
    <ul>
      {users.map(user => (
        <li key={user.id}>{user.name}</li>
      ))}
    </ul>
  );
}
```

---

### Axios vs Fetch

| বিষয় | Axios | Fetch |
|---|---|---|
| **JSON auto parse** | ✅ | ❌ manually করতে হয় |
| **Error handling** | ✅ 4xx/5xx catch করে | ❌ manually করতে হয় |
| **Request cancel** | ✅ | ✅ |
| **Timeout support** | ✅ | ❌ |
| **Browser support** | ✅ সব browser | ✅ modern browser |

---

### Base URL Config (Optional)
```jsx
// api.js
import axios from 'axios';

const api = axios.create({
  baseURL: 'https://your-api.com',
  timeout: 5000,
  headers: { 'Authorization': `Bearer ${token}` }
});

export default api;

// ব্যবহার
import api from './api';
const res = await api.get('/users');
```

---

### Error Handling
```jsx
try {
  const res = await axios.get('/api/users');
  console.log(res.data);
} catch (error) {
  if (error.response) {
    // Server error (4xx, 5xx)
    console.log(error.response.status);
  } else if (error.request) {
    // Network error
    console.log("Network error!");
  }
}
```

---

> 🔗 Official Docs: [axios-http.com](https://axios-http.com/)


---
> 💡 **Tip:** Bookmark these resources — they will save you hours of development time!
