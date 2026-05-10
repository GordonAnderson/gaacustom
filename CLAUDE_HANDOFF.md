# GAA Custom Electronics — Website Development Handoff
## Context Document for Claude AI Sessions

Paste this document along with `index.html` at the start of any new Claude chat session to resume website development without losing context.

---

## Project Overview

**Client:** GAA Custom Electronics, LLC (GAACE)  
**Owner:** Gordon Anderson (Founder & Principal Engineer)  
**Website:** https://www.GAAcustom.com  
**GitHub repo:** https://github.com/GordonAnderson/gaacustom  
**GitHub Pages URL:** https://GordonAnderson.github.io/gaacustom  
**Email:** gaa@gaa-ce.com  
**Phone:** 509.628.6851  
**Address:** 101904 Wiser Pkwy, Suite 105, Kennewick, WA 99338  

---

## Business Description

GAA Custom Electronics develops custom electronics monitoring and control systems for **mass spectrometry research**. Founded 2014. Family business — Gordon (engineering), Christopher Anderson (mechanical/3D printing), Meri Anderson (administration).

**Primary product:** MIPS (Modular Intelligent Power Sources) — a modular, software-configurable control platform for ion optics, RF drive, DC bias, traveling wave, FAIMS, and more.

**Customers:** Universities, national laboratories, pharmaceutical companies, and instrument manufacturers (Bruker, Thermo Fisher, Agilent). 200+ systems deployed in 16+ countries.

---

## Brand & Design

**Colors:**
- Red: `#CC1F1F` (primary accent)
- Dark charcoal: `#1A1A1C` (hero/contact backgrounds)
- White: `#FFFFFF`
- Surface: `#F7F7FA` (light sections)

**Fonts (Google Fonts):**
- Display/headings: `Fraunces` (serif, italic for emphasis)
- Body: `DM Sans`
- Labels/mono: `DM Mono`

**Design pattern:** Hybrid dark/light — dark hero section transitions via SVG wave into light body. Dark contact section and darkest footer bookend the page. This was a deliberate design decision after testing both full dark and full light versions.

**Logo:** Red/charcoal circular logo with white waveform. File: `images/logo.jpeg`. Also embedded as base64 in nav and footer for reliability.

**Favicon:** Located in `favicons/` folder — favicon.ico, 16/32/96px PNGs, apple-touch-icon (180px), 192px PNG.

---

## Technical Architecture

**Single-page site** — `index.html` only. No build tools, no frameworks, no npm. Pure HTML/CSS/JS.

**Hosting:** GitHub Pages — free, automatic SSL via Let's Encrypt (auto-renews every 90 days).

**DNS:** GoDaddy manages GAAcustom.com. Four A records → GitHub IPs (185.199.108-111.153). CNAME www → GordonAnderson.github.io.

**Analytics:** Google Analytics G-TBTBP7GLEK (business Google account).

**Search Console:** Verified, sitemap.xml submitted.

**Price management:** All prices stored in `prices.json` in repo root. Loaded by JavaScript on page load with fallback values hardcoded in index.html. To update any price — edit prices.json on GitHub only, never touch index.html for price changes.

**Map:** Leaflet.js with CartoDB Positron tiles (no API key, works locally and on GitHub Pages). 64 deployment locations, 16 countries. Loaded dynamically via script.onload to avoid "L is not defined" error.

---

## File Structure

```
gaacustom/
├── index.html                    ← entire website
├── prices.json                   ← all product/module prices
├── sitemap.xml                   ← Google sitemap
├── CNAME                         ← contains: www.GAAcustom.com
├── README.md                     ← GitHub repo documentation
│
├── favicons/
│     ├── favicon.ico
│     ├── favicon-16x16.png
│     ├── favicon-32x32.png
│     ├── favicon-96x96.png
│     ├── apple-touch-icon.png
│     └── favicon-192x192.png
│
├── images/
│     ├── logo.jpeg               ✓
│     ├── mips-front.jpg          ✓
│     ├── mips-rear.jpg           ✓
│     ├── mips-internal.jpg       ✓
│     ├── mips-home.jpg           ✓ MIPS host app screenshot
│     ├── control-panel-1.jpg     ✓ 2 RF 24 DCbias 1 ESI
│     ├── control-panel-2.jpg     ✓ 2 RF 16 DCbias Astraea
│     ├── rf-generator.jpg        ✓
│     ├── rf-mega.jpg             ✓
│     ├── mft.jpg                 ✓
│     ├── slim-reverser.jpg       ✓
│     ├── electrometer.jpg        ✓
│     ├── fet-switch.jpg          ✓
│     ├── soft-landing.jpg        ✓ GAACE soft landing system
│     ├── slim-wsu.jpg            ✓ WSU 8-meter SLIM system
│     ├── og-preview.jpg          ✓ Open Graph social preview
│     ├── lab-facility.jpg        ○ pending
│     └── team.jpg                ○ pending
│
└── docs/
      ├── mips/                   ○ 16 PDFs pending upload
      ├── software/               ○ 3 PDFs pending upload
      ├── standalone/             ○ 8 PDFs pending upload
      └── resources/              ○ 3 PDFs pending upload
```

See README.md in the repo for complete filename list for all pending PDFs.

---

## Website Sections (in order)

1. **Nav** — fixed, dark on hero / transitions to white on scroll. Logo + links + "Request Quote" CTA.
2. **Hero** — dark background, animated grid, red glow. MIPS panel card on right.
3. **Wave divider** — SVG wave transitioning dark hero to light body.
4. **Marquee** — red scrolling strip with product names.
5. **Products** — MIPS featured card (front panel banner + home app screenshot on left; description + rear/internal tab switcher on right). Then 6 standalone product cards with photos.
6. **MIPS Modules accordion** — 6 collapsible categories: DC Bias, RF Driver & Heads, Waveform & Pulse, Ion Mobility & FAIMS, Specialty Voltage, Digital & System. Prices loaded from prices.json.
7. **Software Architecture** — "One Interface. Every Instrument." Light background. Inline SVG diagram showing host app → communication bus → MIPS controllers + standalone instruments → custom GUI panel. Two control panel screenshots shown side by side below diagram.
8. **Applications** — two examples so far: (1) GAACE soft landing system, (2) Prof. Brian Clowers WSU 8-meter SLIM system. Layout alternates photo left/right.
9. **Global Deployments** — Leaflet interactive map. Stats: 200+ systems, 16+ countries, 64+ institutions, 10+ years. 64 pins. CartoDB Positron tiles.
10. **Testimonials** — dark background section. Currently one testimonial: Dr. Brian Clowers, Professor of Chemistry, WSU. Links to his faculty page.
11. **Capabilities** — "From Problem to Solution." 4-step process + 6 capability cards grid.
12. **About** — company story + team cards (Gordon, Christopher, Meri).
13. **Downloads** — accordion style, 4 categories: MIPS System (16 docs), MIPS Host Software (5 items), Standalone Instruments (8 docs), Technical & Business (3 docs). PDFs not yet uploaded to GitHub but links are wired up with correct filenames.
14. **Contact** — dark background. Contact details + Google Maps embed (101904 Wiser Pkwy, Kennewick WA) + contact form (mailto: gaa@gaa-ce.com).
15. **Footer** — darkest background. Links + contact info.

---

## Redirect Pages (in repo root)

These handle old Google Business profile URLs with trailing slashes:
- `about/index.html` → `/#about`
- `resources/index.html` → `/#support`
- `capabilities/index.html` → `/#capabilities`
- `profile/index.html` → `/#about`
- `about.html` → `/#about` (handles without trailing slash too)
- `resources.html` → `/#support`
- `capabilities.html` → `/#capabilities`
- `profile.html` → `/#about`

---

## Key People & Testimonials

**Dr. Brian Clowers**
- Title: Professor of Chemistry
- Institution: Washington State University
- Profile: https://chem.wsu.edu/people/staff/wsu-profile/brian.clowers/
- System: 8-meter SLIM, 3 MIPS systems + RF generator + multiple TW Reversers
- Photo on site: `images/slim-wsu.jpg`
- Testimonial on site: Yes — "withstands student abuse...free us up to think about what we will do, not whether our ideas are possible."

---

## Deployment Map Data

64 locations across 16 countries through invoice #1,035. Countries: USA, Canada, UK, Germany, France, Netherlands, Switzerland, Sweden, South Korea, China, Taiwan, Luxembourg, Austria, Finland.

Notable customers visible in data: PNNL (Richland WA), Bruker (Billerica MA), Thermo Fisher (San Jose CA + Hillsboro OR), Agilent (Santa Clara CA), NASA Goddard (Greenbelt MD), Harvard (Cambridge MA), Michigan State FRIB (East Lansing MI), EPFL (Lausanne), DESY (Hamburg), POSTECH (South Korea), Synchrotron SOLEIL (France), IONICON (Innsbruck), ETH Zürich.

To add more pins: provide a list of city/state or city/country and Claude will add coordinates to the locations array in the Leaflet script.

---

## Prices System

All prices in `prices.json`. Key names:

```
mips_range, rf_generator, rf_mega, mft, slim_reverser, 
fet_switch, electrometer, dc50, dc250, dc750, rfdrv, rfhqh,
uprfhqh, twaverf, rf_quad_head, twave, arb, psg, faims_system,
quad_module, esi_b, esi_c, filament, dac, adc, dio_iso, levdet,
ethernet, wifi, interlock, heater, consulting_rate
```

To update: edit prices.json on GitHub only. index.html contains fallback values and loads prices.json on page load.

---

## Social Media & Marketing

**LinkedIn:** Active — Gordon Anderson personal profile. First two posts performed well:
1. Website launch announcement
2. WSU SLIM system application spotlight (with Dr. Clowers photo)

**LinkedIn strategy:** Post 2-3x/month rotating: product spotlights, application examples, behind-the-scenes, customer success, technical tips, milestones. Put URLs in first comment (not post body) for better reach.

**Google Business:** Profile active. Links updated to new domain. Redirect pages handle old /about/, /capabilities/ etc. URLs.

**Content coming:** More customer testimonials, more customer lab photos, application notes.

---

## Outstanding To-Do Items

- [ ] Upload all PDFs to docs/ folders (see README.md for filenames)
- [ ] More customer testimonials (emails sent to select customers)
- [ ] Customer lab photos for Applications section
- [ ] Module list corrections from Gordon (detailed list promised)
- [ ] GitHub MIPS software repo URL (to update 4 software download links from generic github.com/GordonAnderson to specific repo)
- [ ] Lab/facility photo for About section
- [ ] Team photos (optional)
- [ ] More sales location data (invoices 1,036+)
- [ ] Additional application examples (FAIMS, quadrupole MS, ion funnels)

---

## How to Update the Site

**For content/design changes:**
1. Paste this document + index.html into a new Claude chat
2. Describe what you want changed
3. Claude outputs updated index.html
4. Upload to GitHub (drag over existing file → Commit)
5. Live in ~60 seconds

**For price changes:**
Edit prices.json on GitHub only — never need to touch index.html

**For new photos:**
Upload photo here in chat → Claude processes and optimizes it → adds to index.html with correct img tag → you upload both index.html and the photo to GitHub

**For new PDFs:**
Rename to exact filename from README.md → upload to correct docs/ subfolder on GitHub → download link goes live automatically, no HTML change needed

**For new map locations:**
Provide city/state or city/country list → Claude adds pins to the Leaflet locations array

**For new testimonials:**
Provide quote text, name, title, institution, and optionally a profile URL → Claude adds a new card to the Testimonials section

---

## Important Notes for Claude

- The site uses **data-price** attributes on all price elements — never hardcode prices directly in HTML, always use `<span data-price="key">fallback</span>` format and add the key to prices.json
- The Leaflet map script uses `script.onload` pattern — never call L.map() outside the `initDeployMap()` function
- The nav color transition (dark over hero → white on scroll) uses `nav.classList.toggle('scrolled', window.scrollY > 80)` — preserve this
- The MIPS featured card left panel uses flexbox column layout with front panel banner on top and mips-home.jpg below — don't revert to the old fixed-height layout
- All external links (GitHub, Google Maps, WSU faculty pages) use `target="_blank"`
- The `toggleDL()` function handles the downloads accordion, `toggleCat()` handles the modules accordion — both must be preserved
- Google Analytics ID: G-TBTBP7GLEK — already in the `<head>`
- Favicon tags already in `<head>` referencing `favicons/` folder
- Open Graph tags already in `<head>` referencing `images/og-preview.jpg`
- Sitemap reference already in `<head>`
