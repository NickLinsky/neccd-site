# NECCD Website

New England Cycling Coalition for Diversity — built with Astro + Decap CMS, hosted on Netlify.

---

## Deploying to Netlify (step by step)

### What you'll need
- A free [GitHub](https://github.com) account
- A free [Netlify](https://netlify.com) account

---

### Step 1 — Put the project on GitHub

1. Go to [github.com](https://github.com) and sign in
2. Click the **+** icon → **New repository**
3. Name it `neccd-site`, set it to **Public**, click **Create repository**
4. On your computer, unzip this project folder
5. Follow the "push an existing repository" instructions GitHub shows you
   (or ask Claude to walk you through it — just paste those instructions in)

---

### Step 2 — Connect Netlify to GitHub

1. Go to [netlify.com](https://netlify.com) and sign in (or create a free account)
2. Click **Add new site** → **Import an existing project**
3. Choose **GitHub** and authorize Netlify
4. Select the `neccd-site` repository
5. Build settings will auto-fill from `netlify.toml` — leave them as-is
6. Click **Deploy site**

Your site will be live at a URL like `https://something-random.netlify.app` within about a minute.

You can rename it: **Site configuration** → **Change site name** → e.g. `neccd-new`

---

### Step 3 — Enable the CMS (Decap CMS)

1. In Netlify, go to **Integrations** → search for **Identity** → **Enable**
2. Go to **Integrations** → search for **Git Gateway** → **Enable**
3. Go to **Identity** → **Invite users** → enter your email address
4. Check your email and accept the invite — this creates your CMS login

Now you can log in at `https://your-site.netlify.app/admin` to add events and news.

---

## Adding a new event (no coding required)

1. Go to `https://your-site.netlify.app/admin`
2. Log in with your email and password
3. Click **Events** → **New Event**
4. Fill in:
   - **Title** — name of the event
   - **Date** — pick from calendar
   - **Time** — e.g. `9:00 – 11:30 AM`
   - **Location** — full address or landmark
   - **Category** — Ride, Community, Advocacy, or Resources
   - **Cost** — e.g. `Free` (optional)
   - **Contact email** — optional
   - **Short description** — 1–2 sentences, shown in listings
   - **Full description** — the full event details (supports formatting)
5. Click **Publish** — the site rebuilds and goes live in ~30 seconds

---

## Adding a news post

Same as events — go to `/admin`, click **News** → **New News**, fill in the fields, and publish.

---

## Making design changes

Design changes require editing the `.astro` files in the `src/` folder. You can:
- Ask Claude to make specific changes and paste in the updated file
- Or hire a developer for ongoing maintenance

---

## Switching neccd.bike to this site (when you're ready)

1. In Netlify → **Domain management** → **Add custom domain** → enter `neccd.bike`
2. Netlify will show you DNS records to update
3. Log in to wherever your domain is registered (GoDaddy, Namecheap, etc.)
4. Update the DNS records as Netlify instructs
5. Netlify handles the SSL certificate automatically

The old WordPress site will stop serving once DNS propagates (usually within an hour).

---

## Project structure

```
neccd-site/
├── src/
│   ├── content/
│   │   ├── events/        ← one .md file per event
│   │   └── news/          ← one .md file per news post
│   ├── layouts/
│   │   └── Base.astro     ← header, footer, nav
│   ├── pages/
│   │   ├── index.astro    ← homepage
│   │   ├── events/        ← events listing + detail pages
│   │   ├── news/          ← news listing + detail pages
│   │   ├── about.astro
│   │   └── contact.astro
│   └── styles/
│       └── global.css
├── public/
│   ├── admin/             ← Decap CMS (do not edit)
│   ├── images/            ← uploaded images go here
│   └── favicon.svg
├── astro.config.mjs
├── netlify.toml
└── package.json
```
