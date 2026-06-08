# JCSuite

Your personal toolkit — TabSplit, PerkPulse, PackPal, GiftVault, RepBook.

## Widgets

| Widget | What it does |
|--------|-------------|
| **TabSplit** | Split restaurant bills by what each person ordered, with proportional tax + tip |
| **PerkPulse** | Track credit card benefits, usage, and expiry dates |
| **PackPal** | Trip packing checklists from templates, with notes and quantity editing |
| **GiftVault** | Gift idea tracker with occasion reminders |
| **RepBook** | Workout logger with PR tracking and bodyweight chart |

---

## Deploying to Vercel (recommended)

### Step 1 — Push to GitHub

1. Go to [github.com](https://github.com) and create a free account if you don't have one
2. Click **New repository** → name it `jcsuite` → click **Create repository**
3. On your computer, open Terminal and run:

```bash
# Navigate to this folder (wherever you saved it)
cd path/to/jcsuite

# Initialize git and push
git init
git add .
git commit -m "Initial JCSuite"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/jcsuite.git
git push -u origin main
```

### Step 2 — Deploy on Vercel

1. Go to [vercel.com](https://vercel.com) and sign up with your GitHub account
2. Click **Add New → Project**
3. Select your `jcsuite` repository
4. Leave all settings as default (Vercel auto-detects it as a static site)
5. Click **Deploy**

You'll get a URL like `jcsuite.vercel.app` in about 30 seconds. That's your live app.

### Step 3 — Custom domain (optional)

In Vercel → your project → Settings → Domains, you can add a custom domain like `jcsuite.yourdomain.com` for free.

---

## Adding to your phone (PWA)

Once deployed on Vercel:

**iPhone:**
1. Open Safari and go to your Vercel URL
2. Tap the Share button (box with arrow)
3. Scroll down → tap **Add to Home Screen**
4. Name it **JCSuite** → tap **Add**

It'll appear on your home screen like a native app, opening full-screen with no browser UI.

**Android:**
1. Open Chrome and go to your Vercel URL
2. Tap the three-dot menu → **Add to Home screen**

---

## Making updates

Whenever you want to update the app:

1. Edit `index.html`
2. Run:
```bash
git add .
git commit -m "Update description"
git push
```

Vercel auto-deploys on every push. Your phone gets the update automatically next time you open the app.

---

## Adding Firebase for cross-device sync (future)

Right now all data lives in memory and resets on page refresh. To persist data across devices:

1. Create a free project at [firebase.google.com](https://firebase.google.com)
2. Enable **Firestore** and **Authentication** (Google sign-in)
3. Add the Firebase SDK to `index.html`
4. Replace the in-memory arrays (`ppCards`, `pkTrips`, `gvPeople`, `rbWorkouts`, etc.) with Firestore reads/writes

This is a future step — the app is fully functional as-is for session use.

---

## Notes

- **Icons**: The `manifest.json` references `icon-192.png` and `icon-512.png`. You can create these with any image editor (just make a square JCSuite logo at those sizes) or skip them — the PWA will still work, it just won't have a custom icon.
- **Dark mode**: Automatically follows your device's system setting.
- **Mobile**: The sidebar collapses to icons-only on narrow screens.
