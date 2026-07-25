# 🧾 Invoice Generator Pro V3

A professional, client-side invoice generator with subscription-based Pro features. Built entirely with HTML, CSS, and JavaScript — no backend required.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-View%20App-blue?style=flat-square&logo=github)](https://isaacjace116.github.io/invoice-generator-pro-v3-/)

---

## ✨ Features

### Free Tier
- ✅ Create unlimited invoices
- ✅ Add company logo (image upload)
- ✅ Multi-currency support (ZAR, USD, EUR, GBP)
- ✅ Auto-calculate subtotals, tax, and grand total
- ✅ Customizable notes & payment terms
- ✅ Export invoices as PDF
- ✅ Save invoices locally (per-user storage)
- ✅ Responsive mobile design

### Pro Subscription
- 🚀 7-day free trial for new users
- 💳 Secure payments via **PayFast** (South Africa)
- 📧 Password reset via **EmailJS**
- 🔐 User authentication (email + Google Sign-In)
- ☁️ Cloud-synced invoices across devices

---

## 🚀 Getting Started

### Live App
Visit the live app here: **[https://isaacjace116.github.io/invoice-generator-pro-v3-/](https://isaacjace116.github.io/invoice-generator-pro-v3-/)**

### Local Development
Since this is a pure client-side app, you can run it locally by simply opening `index.html` in any modern browser:

```bash
git clone https://github.com/IsaacJace116/invoice-generator-pro-v3-.git
cd invoice-generator-pro-v3-
# Open index.html in your browser
```

No build step, no server, no dependencies to install.

---

## 💳 Payment Integration

Payments are processed securely through **PayFast Sandbox** for testing:

| Plan | Price | Period |
|------|-------|--------|
| Weekly | R 29 | 7 days |
| Monthly | R 99 | 30 days |
| Yearly | R 699 | 365 days (Save 40%) |

**Payment flow:**
1. User selects a plan on the subscription screen
2. Form submits to PayFast sandbox
3. User completes test payment
4. PayFast redirects to `Payment-success.html`
5. Subscription is activated automatically

> **Note:** The app currently uses PayFast Sandbox. For production, switch to live credentials.

---

## 🔐 Authentication

- **Email/Password:** Local storage-based auth
- **Google Sign-In:** Simulated Google OAuth flow
- **Password Reset:** Temporary passwords sent via EmailJS

---

## 📁 Project Structure

```
invoice-generator-pro-v3-/
├── index.html              # Main app (auth + invoice editor + subscription)
├── Payment-success.html   # PayFast success redirect
├── Payment-cancelled.html # PayFast cancel redirect
├── Change-password.html   # Password change after reset
└── README.md              # This file
```

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| HTML5 | Structure & semantic markup |
| CSS3 | Styling with CSS variables & flex/grid |
| Vanilla JavaScript | All app logic (no frameworks) |
| jsPDF | PDF export |
| jsPDF-AutoTable | PDF table generation |
| EmailJS | Password reset emails |
| PayFast API | Payment processing |
| localStorage | Client-side data persistence |

---

## 📱 Mobile-First Design

Built and tested on mobile devices. The app is fully responsive and works great on:
- 📱 Smartphones (portrait & landscape)
- 💻 Tablets
- 🖥️ Desktop browsers

---

## 🔒 Privacy & Security

- **No server** — all data stays in your browser's localStorage
- **No tracking** — no analytics, no cookies, no third-party scripts (except payment & email SDKs)
- **Secure payments** — PayFast handles all payment data; we never see card details
- **Per-user isolation** — each user's invoices are stored under their unique email key

---

## 📝 License

This project is open source. Feel free to fork, modify, and use for your own projects.

---

## 👤 Author

**Lerato Rasetsoke** ([IsaacJace116](https://github.com/IsaacJace116))

Built on a Huawei nova Y70 using Acode, Chrome, and GitHub Pages.

---

## 🙏 Support

If you find this app useful, consider supporting its development:

[![Buy Me a Coffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-Support-yellow?style=flat-square&logo=buy-me-a-coffee)](https://www.buymeacoffee.com/isaacjace116)

---

*Invoice Generator Pro V3 — Create professional invoices in seconds.*
 
