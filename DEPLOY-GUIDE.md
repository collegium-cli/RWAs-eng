# COLLEGIUM — Full Deployment Guide
## Upload to GitHub + Deploy on Vercel (No Terminal Needed)

---

## What's Inside This ZIP

```
collegium-deploy/
  ├── index.html      ← Your full website (all 100 funds, trade popup, vote popup)
  ├── logo.png        ← Your Collegium logo
  ├── logo192.png     ← App icon for mobile
  └── favicon.ico     ← Browser tab icon
```

All 4 files go together. Don't skip any.

---

## STEP 1 — Create a GitHub Account (skip if you have one)

1. Open your browser, go to **github.com**
2. Click **"Sign up"**
3. Enter your email, create a password, pick a username
4. Verify your email
5. Done — you're on GitHub

---

## STEP 2 — Create a New Repository

1. After logging in, look at the **top-right corner**
2. Click the **"+"** button → click **"New repository"**
3. Fill in:
   - **Repository name:** `collegium-app`
   - **Description:** `Tokenized RWAs & Money Market on Solana`
   - **Public** ← keep this selected
   - Do NOT check "Add a README file"
4. Click the green **"Create repository"** button

You'll see a page with setup instructions. Look for the blue link that says:

> **"uploading an existing file"**

Click that link.

---

## STEP 3 — Upload Your Files to GitHub

1. After clicking "uploading an existing file", you'll see a drag-and-drop area
2. **Unzip** the `collegium-deploy.zip` file on your computer first
3. Open the `collegium-deploy` folder
4. **Select ALL 4 files** inside:
   - `index.html`
   - `logo.png`
   - `logo192.png`
   - `favicon.ico`
5. **Drag and drop** all 4 files into the GitHub upload area
6. Wait for all uploads to finish (you'll see 4 green checkmarks)
7. At the bottom, click the green **"Commit changes"** button

**IMPORTANT:** Upload the 4 files directly — NOT the folder. The files must be at the root level of your repo.

After committing, your repo should look like:

```
collegium-app/
  ├── index.html
  ├── logo.png
  ├── logo192.png
  └── favicon.ico
```

If it looks like `collegium-app/collegium-deploy/index.html` — that's wrong. Delete and re-upload just the 4 files.

---

## STEP 4 — Create a Vercel Account

1. Open a new tab, go to **vercel.com**
2. Click **"Sign Up"**
3. Choose **"Continue with GitHub"** ← this is the easiest way
4. Authorize Vercel to access your GitHub
5. Done — you're on Vercel

---

## STEP 5 — Import Your Project

1. On the Vercel dashboard, click **"Add New..."** → **"Project"**
2. You'll see a list of your GitHub repos
3. Find **`collegium-app`** and click **"Import"**

---

## STEP 6 — Configure & Deploy

This is the most important step. You need to change ONE setting:

1. You'll see a "Configure Project" screen
2. Find **"Framework Preset"** → change it to **`Other`**
3. Open **"Build and Output Settings"** (click to expand)
4. Find **"Output Directory"** → type a single dot: **`.`**
5. Leave everything else as default
6. Click **"Deploy"**

Wait about 30 seconds. You'll see a confetti animation when it's done!

---

## STEP 7 — Your Site is Live!

After deployment, Vercel gives you a URL like:

> **https://collegium-app.vercel.app**

Click it. Your Collegium website is now live on the internet!

---

## STEP 8 — Custom Domain (Optional)

Want to use your own domain like `collegium.fun`?

1. In Vercel dashboard → click your project
2. Go to **"Settings"** tab → **"Domains"**
3. Type your domain name → click **"Add"**
4. Vercel will show you DNS records to add
5. Go to your domain registrar (Namecheap, GoDaddy, etc.)
6. Add the DNS records:
   - **Option A:** Add a `CNAME` record → `cname.vercel-dns.com`
   - **Option B:** Add an `A` record → `76.76.21.21`
7. Wait 5-30 minutes for DNS to propagate
8. Done — your custom domain is connected!

---

## How to Update Your Website Later

Whenever you want to make changes:

1. Go to **github.com** → your `collegium-app` repo
2. Click on **`index.html`**
3. Click the **pencil icon** (top-right of the file view) to edit
4. Make your changes
5. Click **"Commit changes"** (green button)
6. Vercel automatically re-deploys in ~30 seconds!

To replace the entire file:
1. Delete the old `index.html` on GitHub (click file → click trash icon → commit)
2. Upload the new `index.html` (click "Add file" → "Upload files")

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| **Blank page on Vercel** | Make sure "Output Directory" is set to `.` (a single dot) |
| **404 Not Found** | Make sure `index.html` is at the ROOT of your repo, not inside a subfolder |
| **Logo not showing** | Make sure `logo.png` was uploaded to the same level as `index.html` |
| **Favicon not showing** | Hard refresh your browser (Ctrl+Shift+R) |
| **Wallet won't connect** | User needs Phantom/Solflare/Backpack browser extension installed |
| **Can't find repo on Vercel** | Make sure you signed into Vercel with the SAME GitHub account |
| **Trade popup → Helius prompt** | This is by design — users need an RPC API key for on-chain trades |
| **Vercel says "Build Error"** | Change Framework Preset to "Other" and Output Directory to "." |

---

## Quick Summary

```
Step 1  →  Create GitHub account       (github.com)
Step 2  →  Create new repository        (name it: collegium-app)
Step 3  →  Upload 4 files               (drag & drop all 4)
Step 4  →  Create Vercel account         (vercel.com → sign up with GitHub)
Step 5  →  Import the repo              (click "Import")
Step 6  →  Set Output Directory to "."   (single dot) → Deploy
Step 7  →  Your site is live!           (collegium-app.vercel.app)
```

Total time: about 5 minutes. No coding. No terminal. Just browser clicks.
