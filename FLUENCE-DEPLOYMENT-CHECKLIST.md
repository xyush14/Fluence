# 🚀 Fluence Deployment Checklist

## ✅ You have:
- [x] Domain: `fluence.lol` (from UltraHost)
- [x] Landing page (index.html)
- [x] Creator app with Google OAuth (app/index.html)
- [x] Hosted on Netlify (free tier)

## 📋 Next: 4 Simple Steps

---

## **STEP 1: Fix fluence.lol 404 Error** (10 mins)

**Problem:** You're seeing "404 Not Found" or can't reach fluence.lol

**Solutions (try in order):**

### A) Check DNS Propagation
- Visit https://whatsmydns.net
- Search: `fluence.lol`
- Select: **NS** record
- If NOT all green → **wait 2-4 more hours**, DNS is still propagating
- If all green → continue to B

### B) Clear Browser Cache
1. Open DevTools (F12)
2. Go to **Network** tab
3. Check "**Disable cache**"
4. Hard refresh (Cmd+Shift+R or Ctrl+Shift+R)
5. Reload `fluence.lol`

### C) Verify Netlify Domain Setup
1. Log into Netlify → Your Fluence site
2. Go to **Domain Management**
3. Check you have:
   - `fluence.lol` (primary) ✓
   - `app.fluence.lol` (subdomain) ✓
4. Both should show a checkmark ✓

### D) Test Direct Netlify URL
- Find your Netlify site URL (looks like `charming-walrus-abc123.netlify.app`)
- Visit it directly — does it show the landing page?
- If **YES** → DNS issue, wait 12-48 hrs
- If **NO** → GitHub/Netlify deploy issue

---

## **STEP 2: Set Up Firebase + Google OAuth** (15 mins)

**Open:** `FIREBASE-SETUP-QUICK.html` (in your deploy folder)
- This has EXACT step-by-step instructions
- Follow it to get your 2 keys:
  1. **Firebase Config** (JSON object with apiKey, authDomain, etc.)
  2. **Google Client ID** (string like 123456...apps.googleusercontent.com)

---

## **STEP 3: Paste Keys into App** (2 mins)

**In `app/index.html`:**

### Find Line 20-27 (Firebase Config):
```javascript
FIREBASE_CONFIG: {
  apiKey: "AIzaSyDEXAMPLE_PASTE_YOUR_API_KEY_HERE",
  authDomain: "fluence-abc123.firebaseapp.com",
  projectId: "fluence-abc123",
  storageBucket: "fluence-abc123.appspot.com",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:abcdef1234567890",
},
```

**Replace with your actual values from Firebase Console**

### Find Line 273 (Google Client ID):
```javascript
client_id: "YOUR_GOOGLE_CLIENT_ID.apps.googleusercontent.com",
```

**Replace with your actual Google Client ID**

✅ **SAVE FILE**

---

## **STEP 4: Deploy to Netlify** (5 mins)

### Push to GitHub:
```bash
# In your fluence folder:
git add app/index.html
git commit -m "Add Google OAuth with Firebase config"
git push origin main
```

### Netlify Auto-Deploys:
- Your changes go live in 2-5 minutes
- Check Netlify Dashboard → Deployments to watch progress
- Once green ✓, visit `app.fluence.lol` to test

---

## ✨ **Testing the Live App**

Once deployed, test this flow:

1. **Visit:** `app.fluence.lol`
2. **Click:** "Sign in with Google" button
3. **Log in** with any Google account (your Gmail, etc.)
4. **Fill in:**
   - Name: (your name)
   - City: (e.g., Gwalior)
   - Instagram: (optional, like @yourhandle)
   - YouTube: (optional)
5. **Click:** "Continue to Deals"
6. **See:** 4 mock deals (Cafe Mocha, FitHub Gym, StyleBoutique, TravelHub)
7. **Apply** to a deal
8. **Go to Profile** tab → See your info saved
9. **Refresh page** → You stay logged in ✓

---

## 🔴 **If You Get Errors:**

| Error | Fix |
|-------|-----|
| "Sign in with Google" button doesn't show | Firebase config has typo → check console (F12) for errors |
| "Origin not allowed" when clicking sign-in | Add `fluence.lol` & `app.fluence.lol` to Google Cloud Console → Credentials → Authorized origins |
| Login works but "Continue to Deals" button is grayed out | Name field is empty — fill it in |
| Profile saves, but doesn't reload after refresh | Normal! We're using browser storage for now. Real database coming next. |

---

## 📝 **Summary: What's Live Now**

| URL | What | Status |
|-----|------|--------|
| `fluence.lol` | Landing page (crazier version, no Gwalior refs) | ✅ Deployed |
| `app.fluence.lol` | Creator app (Google OAuth + mock deals) | ✅ Ready (after Firebase setup) |
| WhatsApp | +91 88156 21916 | ✅ In app everywhere |

---

## 🎯 **Phase 2 (After This Works)**

Once creators are signing in with Google:
1. Replace mock deals with real deals (Google Sheets backend)
2. Add Instagram/YouTube OAuth linking
3. Create brand signup & deal posting flow
4. Set up permanent data storage (Google Sheets + Apps Script)

---

**Questions?** WhatsApp: +91 88156 21916 | Email: fluence.lol
