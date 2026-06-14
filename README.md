# navnitshukla.github.io

Personal website for [navnitshukla.com](https://navnitshukla.com) — hosted on GitHub Pages.

## Local Development

Open `index.html` directly in a browser, or use a local server:

```bash
npx serve .
# or
python3 -m http.server 8080
```

Then visit `http://localhost:8080`

## Adding Your Profile Photo

1. Add your photo as `assets/images/navnit-profile.jpg` (recommended: 600×800px, portrait)
2. Add book cover images:
   - `assets/images/book-data-wrangling.jpg`
   - `assets/images/book-ai-blueprints.jpg`

The site gracefully falls back to placeholder icons if images are missing.

---

## Deploying to GitHub Pages

### Step 1 — Create the Repository

Create a new **public** repository named exactly:
```
navnitshukla.github.io
```

### Step 2 — Push the Files

```bash
cd /Users/navnitshukla/Documents/personal/website
git init
git add .
git commit -m "Initial commit: personal portfolio site"
git branch -M main
git remote add origin https://github.com/navnitshukla/navnitshukla.github.io.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages

1. Go to the repo on GitHub
2. Click **Settings** → **Pages** (left sidebar)
3. Under **Source**, select `main` branch and `/ (root)` folder
4. Click **Save**

### Step 4 — Configure Custom Domain

In the same **Settings → Pages** screen:
1. Enter `navnitshukla.com` in the **Custom domain** field
2. Click **Save** — GitHub will create the CNAME file automatically (it already exists in this repo)

### Step 5 — Update Your DNS

At your domain registrar (wherever navnitshukla.com is registered), add these DNS records:

**Option A — Apex domain (recommended):**
Add four A records pointing to GitHub Pages IPs:
```
Type: A    Name: @    Value: 185.199.108.153
Type: A    Name: @    Value: 185.199.109.153
Type: A    Name: @    Value: 185.199.110.153
Type: A    Name: @    Value: 185.199.111.153
```

**Option B — CNAME (if using www subdomain):**
```
Type: CNAME    Name: www    Value: navnitshukla.github.io
```

### Step 6 — Enable HTTPS

After DNS propagates (15 min – 24 hours):
1. Return to **Settings → Pages**
2. Check **Enforce HTTPS**

---

## Important Note on Existing navnitshukla.com

Your current WordPress course platform is at `navnitshukla.com/courses`.
After DNS cutover to GitHub Pages, you should move the courses platform to a subdomain:

```
courses.navnitshukla.com
```

Then update the "Browse Courses" link in `index.html` (line with `href="https://navnitshukla.com/courses"`)
to point to the new subdomain URL.
