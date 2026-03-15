# josevasquez.net — Azure Cloud Architect Portfolio

A professional profile website for an Azure Cloud Architect, designed to attract recruiters and showcase cloud projects, skills, and experience.

## 🚀 Deploying to GitHub Pages

### Step 1 — Create a GitHub repository

1. Go to [github.com](https://github.com) and sign in
2. Click **New repository**
3. Name it exactly: `josevasquez.net` (or your GitHub username if using the default domain)
4. Set to **Public**
5. Click **Create repository**

### Step 2 — Push your files

```bash
git init
git add .
git commit -m "Initial commit — portfolio site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/josevasquez.net.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages

1. In your repository, go to **Settings → Pages**
2. Under **Source**, select **Deploy from a branch**
3. Select **main** branch, **/ (root)** folder
4. Click **Save**

### Step 4 — Add your custom domain

1. Still in **Settings → Pages**, under **Custom domain**, enter: `josevasquez.net`
2. Click **Save** — GitHub will add a `CNAME` file automatically

### Step 5 — Configure DNS at your domain registrar

Log in to your domain registrar (GoDaddy, Namecheap, Cloudflare, etc.) and add these DNS records:

| Type  | Name | Value                  |
|-------|------|------------------------|
| A     | @    | 185.199.108.153        |
| A     | @    | 185.199.109.153        |
| A     | @    | 185.199.110.153        |
| A     | @    | 185.199.111.153        |
| CNAME | www  | YOUR_USERNAME.github.io |

DNS changes can take up to 24 hours to propagate.

### Step 6 — Enable HTTPS (recommended)

Once DNS is verified, go back to **Settings → Pages** and check **Enforce HTTPS**.

---

## ✏️ Customising the site

### Personal information
Edit `index.html` and update these sections:

| What to change | Where to find it |
|----------------|-----------------|
| Your name / title | `.hero-title` section |
| Bio paragraphs | `#about` section |
| Certifications | `.cert-row` — add/remove `.cert-chip` divs |
| Stats (years, projects, certs) | `.hero-stats` — update the numbers |
| Email address | `#contact` section — `mailto:` link |
| LinkedIn / GitHub URLs | `#contact` section |

### Projects
Each project is a `.project-card` div in `#projects`. Copy/paste a card block to add more:

```html
<div class="project-card">
  <div class="project-meta">
    <span class="project-tag">Your Tag</span>
    <span class="project-year">2025</span>
  </div>
  <h3 class="project-title">Project Title</h3>
  <p class="project-desc">Project description...</p>
  <div class="project-tech">
    <span>Tech 1</span><span>Tech 2</span>
  </div>
</div>
```

### Experience
Each role is a `.timeline-item` div in `#experience`. Copy/paste to add more roles.

### Skills
Each skill category is a `.skill-card` div in `#skills`. Update the `<ul>` list items inside each card.

### Colours
All design tokens are CSS variables at the top of `style.css` inside `:root {}`.
Key variables:

```css
--accent: #0078d4;   /* Azure blue — change to match your brand */
--bg:     #0d1117;   /* Main background */
--bg-alt: #111820;   /* Alternate section background */
```

To switch to a **light theme**, swap these values:
```css
--bg:      #f8fafc;
--bg-alt:  #f1f5f9;
--bg-card: #ffffff;
--text:    #0f172a;
--text-muted: #64748b;
--text-light: #475569;
--border:  rgba(0,0,0,0.08);
```

---

## 📁 File structure

```
josevasquez.net/
├── index.html      ← All page content and structure
├── style.css       ← All styles and design tokens
├── main.js         ← Nav, scroll effects, animations
├── resume.pdf      ← Add your CV here (linked in Contact section)
└── README.md       ← This file
```

## 🖼️ Adding a profile photo (optional)

1. Add your photo as `profile.jpg` in the root folder
2. In `index.html`, add inside `#about`:

```html
<img src="profile.jpg" alt="Your name" class="profile-photo" />
```

3. Add to `style.css`:

```css
.profile-photo {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  object-fit: cover;
  border: 2px solid var(--border);
}
```
