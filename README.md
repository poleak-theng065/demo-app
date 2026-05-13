# Demo App — Astro + Decap CMS

A production-ready static website built with **Astro** and **Decap CMS**, deployed to **GitHub Pages** with automatic CI/CD.

## 🚀 Live Site

[https://poleak-theng065.github.io/demo-app](https://poleak-theng065.github.io/demo-app)

## 🛠 Admin Panel

[https://poleak-theng065.github.io/demo-app/admin/](https://poleak-theng065.github.io/demo-app/admin/)

Sign in with your **GitHub account** (poleak-theng065) to manage content.

---

## Setup Guide

### 1. Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Under **Source**, select **GitHub Actions**
3. Save

### 2. Enable GitHub OAuth for Decap CMS

Decap CMS needs OAuth to authenticate editors via GitHub.

**Option A — Use Sveltia CMS Auth (easiest, free)**

The `config.yml` already points to `https://sveltia-cms-auth.pages.dev` as the `base_url`. This is a free, open-source OAuth proxy. No setup needed — it works out of the box.

**Option B — Deploy your own OAuth app (optional)**

1. Go to GitHub → Settings → Developer settings → OAuth Apps → **New OAuth App**
2. Fill in:
   - **Homepage URL**: `https://poleak-theng065.github.io/demo-app`
   - **Authorization callback URL**: `https://YOUR_AUTH_PROXY/callback`
3. Note your **Client ID** and **Client Secret**

### 3. Deploy

Push to `main` — GitHub Actions will automatically build and deploy:

```bash
git add .
git commit -m "Initial Astro + Decap CMS setup"
git push origin main
```

### 4. Create Content

1. Visit `/admin/` on your live site
2. Click **Login with GitHub**
3. Create blog posts, manage pages, and update site settings

Every save in the CMS commits directly to this repository.

---

## 🗂 Project Structure

```
demo-app/
├── public/
│   ├── admin/
│   │   ├── index.html        # Decap CMS admin panel
│   │   └── config.yml        # CMS configuration
│   └── images/               # Uploaded media files
├── src/
│   ├── content/
│   │   ├── blog/             # Blog posts (.md files)
│   │   ├── pages/            # Site pages
│   │   └── config.ts         # Astro content collections
│   ├── layouts/
│   │   └── Layout.astro      # Base layout
│   └── pages/
│       ├── index.astro       # Homepage
│       └── blog/
│           ├── index.astro   # Blog listing
│           └── [slug].astro  # Individual post
├── .github/workflows/
│   └── deploy.yml            # GitHub Pages CI/CD
└── astro.config.mjs
```

## 📦 Tech Stack

- [Astro](https://astro.build/) — Static site generator
- [Decap CMS](https://decapcms.org/) — Git-based headless CMS
- [GitHub Pages](https://pages.github.com/) — Hosting
- [GitHub Actions](https://github.com/features/actions) — CI/CD

## Development

```bash
npm install
npm run dev
```

Open [http://localhost:4321/demo-app/](http://localhost:4321/demo-app/)
