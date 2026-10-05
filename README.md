# Franers website

Bilingual (English / Arabic) website for **Franers**, the F&B business growth consultancy in Jeddah and Riyadh.

- `index.html` – the full site (single page, mobile-first, RTL support for Arabic)
- `assets/` – logos, brand mark and team photo
- `assets/clients/` – 113 client logos cropped from the company profile (Jan 2026). Names live in the `CLIENTS` list in `index.html`.
- `assets/video/franers-story.mp4` – the story video in "Who we are"

## v2 changes
- Services: fixed the text-wrapping bug in the step lists; each service now has its own icon layout (tiles, connected journey, timeline, advisory cycle), a photo, deep links (`#service-invest` etc.) and sticky tabs.
- Hero on a Riyadh photo, count-up stats, wave lines, process cards with icons.
- Client logo wall: two scrolling rows plus "View all"; hover or tap shows the brand name.
- Franchise readiness check (6 questions, score, gaps, opens the franchise survey pre-filled).
- Survey submissions: a branded PDF (Franers logo, reference number, tables of the client's details and answers) is generated in the browser and emailed as an attachment to norfali@franers.com and mtabshi@franers.com through FormSubmit. The client can also download a copy.
- Stock photos load from Unsplash (free licence, hotlinked). Replace with your own project photos when available.

## Before launch
1. **Fonts:** the brand fonts Garet, 29LT Bukra and Madani Arabic are licensed. Add their web font files and `@font-face` rules; the site already lists them first and falls back to Lexend, Readex Pro and IBM Plex Sans Arabic from Google Fonts.
2. **Survey emails:** surveys are sent through FormSubmit (free) to norfali@franers.com, with a copy to mtabshi@franers.com. The first submission from the live site sends an activation email to norfali@franers.com; click the link once to start receiving submissions.
3. **Hosting:** upload the folder to any static host and point franers.com at it.

Contacts: info@franers.com · norfali@franers.com · +966 567 111 588
