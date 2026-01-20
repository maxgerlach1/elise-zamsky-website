# Elise Zamsky, PhD - Website

Professional website for a clinical psychology practice.

**Live at:** https://elisezamskyphd.com
**Redirect:** https://elisezamsky.com

---

## Current Setup

### Hosting: Netlify
- **Site name:** beautiful-stardust-1b7e9a
- **Auto-deploys** from GitHub on push to `main`
- **Free SSL** via Let's Encrypt

### Domains: Namecheap
- `elisezamskyphd.com` (primary)
- `elisezamsky.com` (redirects to primary)

Both domains use **Netlify DNS** (nameservers point to Netlify).

### Contact Form: Netlify Forms
- Form submissions appear in Netlify dashboard under **Forms**
- Email notifications configured in Netlify

---

## How to Make Updates

1. Edit files locally
2. Test by opening `index.html` in browser
3. Push to GitHub:
   ```bash
   cd /Users/max.gerlach/projects/elise-zamsky-website
   git add .
   git commit -m "Description of changes"
   git push
   ```
4. Netlify auto-deploys within 1-2 minutes

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
│   └── headshot.jpg    # Professional photo
├── netlify.toml        # Netlify config (redirects)
└── README.md           # This file
```

---

## Setup Reference (How This Was Built)

### 1. GitHub Repository
```bash
git init
git add .
git commit -m "Initial website"
gh repo create elise-zamsky-website --public --source=. --push
```

Repository: https://github.com/maxgerlach1/elise-zamsky-website

### 2. Netlify Deployment
1. Go to [app.netlify.com](https://app.netlify.com)
2. "Add new site" → "Import an existing project"
3. Connect GitHub → select `elise-zamsky-website`
4. Deploy (no build command needed for static HTML)

### 3. Domain Setup (Namecheap)
Purchased both domains at [namecheap.com](https://namecheap.com)

For each domain:
1. In Netlify: Domain settings → Add custom domain
2. Click "Set up Netlify DNS" → get 4 nameservers
3. In Namecheap: Domain List → Manage → Nameservers → Custom DNS
4. Paste the 4 Netlify nameservers:
   ```
   dns1.p05.nsone.net
   dns2.p05.nsone.net
   dns3.p05.nsone.net
   dns4.p05.nsone.net
   ```
5. Save and wait for DNS propagation (5-30 min)

### 4. Contact Form (Netlify Forms)
- Form uses `data-netlify="true"` attribute
- Submissions go to Netlify dashboard → Forms
- Email notifications: Forms → contact → Settings → Add notification

---

## Troubleshooting

**Site not updating after push:**
- Check Netlify dashboard → Deploys for errors
- Make sure GitHub repo is connected

**Form not working:**
- Ensure `data-netlify="true"` is on the form tag
- Submit a test to activate the form in Netlify

**SSL certificate error:**
- Go to Netlify → Domain settings → HTTPS → Renew certificate
- Wait a few minutes for provisioning

**DNS not resolving:**
- Verify nameservers are set correctly in Namecheap
- DNS can take up to 48 hours (usually 5-30 min)
- Flush local DNS: `sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder`
