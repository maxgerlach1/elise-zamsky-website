# Elise Zamsky, PhD - Website

A clean, professional website for a clinical psychology practice.

## Preview Locally

Open `index.html` directly in your browser, or run a local server:

```bash
cd /Users/max.gerlach/projects/elise-zamsky-website
python3 -m http.server 8080
```

Then visit http://localhost:8080

## Setup Checklist

### 1. Add Your Content

Replace placeholder text (marked with `[brackets]`) in these files:

- **index.html** - City/state, welcome message
- **about.html** - Bio, education, approach, credentials
- **services.html** - Specific services offered (add/remove as needed)
- **fees.html** - Session rates, accepted insurance
- **contact.html** - Phone, email, address, office hours
- **All files** - Update footer with correct contact info

### 2. Add Photo

Replace `images/headshot.jpg` with a professional photo of your mom.

Recommended: 600x800px or similar portrait ratio, optimized for web (~100-200KB).

### 3. Set Up Contact Form (Formspree)

1. Go to https://formspree.io and create a free account
2. Create a new form
3. Copy your form ID (looks like `xabcdefg`)
4. In `contact.html`, find this line:
   ```html
   <form action="https://formspree.io/f/YOUR_FORM_ID" ...>
   ```
5. Replace `YOUR_FORM_ID` with your actual form ID

Form submissions will be sent to the email you registered with.

---

## Hosting on Netlify (Recommended)

Netlify offers free hosting with custom domains, SSL, and automatic deployments.

### Step 1: Create GitHub Repository

```bash
cd /Users/max.gerlach/projects/elise-zamsky-website
git init
git add .
git commit -m "Initial website"
```

Create a new repo on GitHub, then:

```bash
git remote add origin https://github.com/YOUR_USERNAME/elise-zamsky-website.git
git branch -M main
git push -u origin main
```

### Step 2: Deploy to Netlify

1. Go to https://netlify.com and sign up (free) with your GitHub account
2. Click "Add new site" > "Import an existing project"
3. Connect your GitHub repo
4. Deploy settings: leave defaults (no build command needed)
5. Click "Deploy site"

Your site will be live at `random-name.netlify.app` within minutes.

### Step 3: Buy Domain

Buy `elisezamskyphd.com` from one of these registrars:

- **Namecheap** (~$10/year) - namecheap.com
- **Cloudflare** (~$9/year) - cloudflare.com/products/registrar
- **Porkbun** (~$9/year) - porkbun.com

### Step 4: Connect Domain to Netlify

1. In Netlify dashboard, go to your site > "Domain settings"
2. Click "Add custom domain"
3. Enter `elisezamskyphd.com`
4. Netlify will give you DNS records to add

At your domain registrar, update DNS:
- Add an A record pointing to Netlify's load balancer IP
- Or change nameservers to Netlify's (simplest option)

Netlify provides free SSL - your site will automatically be served over HTTPS.

---

## Alternative: GitHub Pages (Also Free)

If you prefer GitHub Pages:

1. Push to GitHub as described above
2. Go to repo Settings > Pages
3. Select "main" branch, root folder
4. Your site will be at `username.github.io/elise-zamsky-website`
5. Add custom domain in the same settings area

---

## Future Updates

To update the site:

1. Edit the files locally
2. Test by opening in browser
3. Commit and push to GitHub:
   ```bash
   git add .
   git commit -m "Update content"
   git push
   ```
4. Netlify automatically deploys changes (usually within 1-2 minutes)

---

## File Structure

```
elise-zamsky-website/
├── index.html          # Home page
├── about.html          # About/bio page
├── services.html       # Services offered
├── fees.html           # Insurance & fees
├── contact.html        # Contact form & info
├── css/
│   └── style.css       # All styles
├── images/
│   └── headshot.jpg    # Main photo (replace this)
└── README.md           # This file
```

---

## Need Help?

Common issues:

- **Form not working**: Make sure you replaced `YOUR_FORM_ID` with your actual Formspree form ID
- **Image not showing**: Check that `images/headshot.jpg` exists and the path is correct
- **Styling broken**: Make sure `css/style.css` exists and the link in HTML is correct
