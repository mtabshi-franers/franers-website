# Franers website

Bilingual (English / Arabic) website for **Franers**, the F&B business growth consultancy in Jeddah and Riyadh.

- `index.html` – the full site (single page, mobile-first, RTL support for Arabic)
- `assets/` – logos, brand mark and team photo

## Before launch
1. **Fonts:** the brand fonts Garet, 29LT Bukra and Madani Arabic are licensed. Add their web font files and `@font-face` rules; the site already lists them first and falls back to Lexend, Readex Pro and IBM Plex Sans Arabic from Google Fonts.
2. **Survey submissions:** the site uses Netlify Forms (`franers-survey`). Enable form detection in Netlify, deploy the site, then add email notifications under **Forms → Submission notifications** for `norfali@franers.com` and `mtabshi@franers.com`.
3. **Hosting:** deploy this folder to Netlify and point `franers.com` at the site.

Contacts: info@franers.com · norfali@franers.com · +966 567 111 588
