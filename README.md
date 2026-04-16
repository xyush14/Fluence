# Fluence Platform

**Get paid to post. Fluence connects local creators with local brands.**

A modern web platform for content creators and businesses to collaborate on paid deals.

## 🚀 Live Sites

- **Landing Page**: [fluence.lol](https://fluence.lol)
- **Creator App**: [app.fluence.lol](https://app.fluence.lol)
- **Admin Panel**: [admin.fluence.lol](https://admin.fluence.lol)

## 📁 Folder Structure

```
├── index.html                    # Landing page (fluence.lol)
├── app/index.html               # Creator app (app.fluence.lol)
├── admin-panel.html             # Admin dashboard
├── SETUP-GUIDE.html             # Setup instructions
├── WHATSAPP-BUSINESS-GUIDE.html # WhatsApp Business playbook
└── assets/                      # Logos and brand assets
```

## 🛠️ Technology Stack

- **Frontend**: React 18 + Babel Standalone (single-file HTML architecture)
- **Auth**: Firebase Phone Auth (free 10K SMS/month in India)
- **Backend**: Google Apps Script + Google Sheets
- **Hosting**: Netlify (automatic CI/CD from GitHub)
- **Domains**: Custom domains via Netlify + UltraHost DNS

## 📝 Features

### For Creators
- Browse paid content deals in your city
- One-click applications with phone verification
- Earnings dashboard & deal tracking
- Digital wallet payments (UPI)

### For Brands
- Post deals specifying creators needed, budget, deliverables
- Shortlist creators from database
- Built-in escrow (funds held until delivery verified)
- Analytics on creator reach & engagement

### Admin Panel
- Manage creators and brands
- Approve/reject applications
- Track deal lifecycle & payouts
- Setup guides integrated into dashboard

## ⚙️ Configuration

### Firebase Setup
1. Create a Firebase project at [console.firebase.google.com](https://console.firebase.google.com)
2. Enable Phone Authentication
3. Copy the web config to `app/index.html` → `window.FLUENCE.FIREBASE_CONFIG`

### Google Apps Script Backend
1. Create a new Apps Script project at [script.google.com](https://script.google.com)
2. Deploy `backend/google-apps-script.gs` as a web app
3. Copy the `/exec` URL to `app/index.html` → `window.FLUENCE.API_URL`

### WhatsApp Business
- Number: +91 88156 21916
- Profile setup & quick replies guide: `WHATSAPP-BUSINESS-GUIDE.html`
- Click-to-chat links: `https://wa.me/918815621916?text=...`

## 🌐 Deployment

### First Time Setup
1. Create a GitHub repo: `github.com/YOUR_USERNAME/fluence`
2. Clone and push this folder:
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Fluence platform"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/fluence.git
   git push -u origin main
   ```

3. Connect GitHub to Netlify:
   - Go to [netlify.com](https://netlify.com)
   - New site → Import from GitHub → Select `fluence` repo
   - Build settings: Leave blank (static HTML)
   - Deploy site

### Automatic Deployments
Every push to `main` branch auto-deploys to Netlify. No manual uploads needed.

## 🌍 Domain Setup

### At Netlify
1. Go to Project Settings → Domain Management
2. Add primary domain: `fluence.lol`
3. Add subdomain: `app.fluence.lol` (points to root, will resolve to `/app/index.html`)
4. Netlify gives you nameservers (NS records)

### At UltraHost (DNS)
1. Log into UltraHost domain manager
2. Point nameservers to Netlify's:
   - `dns1.netlify.com`
   - `dns2.netlify.com`
   - `dns3.netlify.com`
   - `dns4.netlify.com`
3. Wait 12-48 hours for DNS propagation

## 📱 WhatsApp Contact

**Fluence Support**: +91 88156 21916

Use this number everywhere:
- Landing page CTAs
- In-app support links
- Email signature
- Brand agreements
- Creator agreements

## 📚 Documentation

- **SETUP-GUIDE.html** — Full backend setup walkthrough
- **WHATSAPP-BUSINESS-GUIDE.html** — WhatsApp Business configuration playbook
- **admin-panel.html** — Admin dashboard with integrated setup instructions

## 📜 Legal

- **Creator Agreement**: `Fluence-Creator-Agreement.docx`
- **Brand Agreement**: `Fluence-Brand-Agreement.docx`
- Both governed by laws of India; jurisdiction: Gwalior Courts

## 💬 Support

Need help? Contact us:
- WhatsApp: +91 88156 21916
- Website: fluence.lol
- Email: (to be configured)

---

**Version 1.0** · Built with ❤️ · Powered by Fluence Platform
