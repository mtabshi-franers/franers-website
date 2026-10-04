# Franers website

Bilingual (English / Arabic) website for **Franers**, the F&B business growth consultancy in Jeddah and Riyadh.

- `index.html` – the full site (single page, mobile-first, RTL support for Arabic)
- `assets/` – logos, brand mark and team photo

## Before launch
1. **Fonts:** the brand fonts Garet, 29LT Bukra and Madani Arabic are licensed. Add their web font files and `@font-face` rules; the site already lists them first and falls back to Lexend, Readex Pro and IBM Plex Sans Arabic from Google Fonts.
2. **Survey emails:** set `FORM_ENDPOINT` in `index.html` to a form-to-email service (e.g. Formspree or FormSubmit) that forwards to norfali@franers.com and mtabshi@franers.com. Until then, the survey opens the visitor's email app with the request pre-addressed.
3. **Hosting:** upload the folder to any static host and point franers.com at it.

Contacts: info@franers.com · norfali@franers.com · +966 567 111 588
