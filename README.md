# Swiftkid Tech Global Link - Vercel Deployment Guide

This is a static multi-page website. No build step required. Will work perfectly on Vercel with same functions as preview here.

## Files to deploy
- index.html (homepage)
- services.html
- portfolio.html
- contact.html
- about.html, terms.html, privacy.html, refund.html
- style.css
- logo.jpg (full logo)
- logo-icon.png (small SK icon - favicon + header)
- hero-agency.png
- portfolio-dano.png, portfolio-spinached.png, portfolio-hydramed.png, portfolio-metapals.png, portfolio-webdiner.png, portfolio-fiverr.png
- vercel.json

## Method 1: Easiest - Drag & Drop (2 mins)

1. Go to https://vercel.com/new
2. Log in with your GitHub / Gmail (same account you used for my-website-portfolio-omega.vercel.app)
3. Click **Browse** → drag your entire project folder (`/home/user` contents) or upload zip
4. Settings:
   - Framework Preset: **Other**
   - Root Directory: `./`
   - Build Command: leave empty
   - Output Directory: leave empty / `./`
5. Click **Deploy** → Vercel gives you URL like `swiftkid-tech-global-link.vercel.app`
6. Done!

## Method 2: Via Vercel CLI (for developers)

```bash
npm i -g vercel
vercel login
# in your project folder
vercel
# follow prompts: set up and deploy? Y, which scope, link to existing? N
# Framework: Other, Build: (none), Output: ./
vercel --prod
```

## Method 3: Via GitHub (Recommended for updates)

1. Create new GitHub repo `swiftkid-tech`
2. Push all files:
```bash
git init
git add .
git commit -m "Swiftkid Tech Global Link launch"
git branch -M main
git remote add origin https://github.com/YOURUSERNAME/swiftkid-tech.git
git push -u origin main
```
3. On Vercel Dashboard → **New Project** → Import your GitHub repo
4. Deploy → auto-deploys on every git push

## Will same functions work?

YES - 100% identical:
- ✅ Responsive mobile menu (hamburger) - client-side JS
- ✅ Page navigation (index ↔ services ↔ portfolio ↔ contact) - simple <a> links
- ✅ Portfolio images - now locally hosted (/portfolio-*.png) so no more broken Vercel external links
- ✅ Contact form - currently shows alert popup. Works on Vercel same way. To make it actually send emails:
   - Option A: Change form action to Formspree (free): `<form action="https://formspree.io/f/YOUR_ID" method="POST">`
   - Option B: I can add a Vercel Serverless Function `/api/contact.js` using Resend / Nodemailer

## Adding Custom Domain

In Vercel Dashboard → Project → Settings → Domains → Add `swiftkidtech.com.ng` or `swiftkidtechgloballink.com`
Then update DNS: Type CNAME, Name www, Value cname.vercel-dns.com

## Important Notes

- Your images are ~2.5MB each (hero-agency.png etc). Vercel allows it but for faster loading you may want me to compress them to ~300KB webp. I can do that on request.
- Contact details already correct: mandiblesolution@gmail.com / +234(0)7036251901 / No 3 Ori Osoko Kemta Abeokuta
- Footer links all point to correct separate pages

Need me to add a working email backend for contact form before you deploy?
