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
**Address:** 101904 Wiser Pkwy, **Suites 105 & 106**, Kennewick, WA 99338  

---

## Business Description

GAA Custom Electronics develops custom electronics monitoring and control systems for **mass spectrometry research**. Founded 2014. Family business — Gordon (engineering), Christopher Anderson (mechanical/3D printing), Meri Anderson (administration).

**Primary product:** MIPS (Modular Intelligent Power Sources) — a modular, software-configurable control platform for ion optics, RF drive, DC bias, traveling wave, FAIMS, and more.

**Customers:** Universities, national laboratories, pharmaceutical companies, and instrument manufacturers (Bruker, Thermo Fisher, Agilent). 200+ systems deployed in 16+ countries.

**Facility:** 1,800 sq ft across two attached suites (105 & 106) at 101904 Wiser Pkwy, Kennewick WA. Includes electronics R&D lab, SMT assembly, machine shop (mill, lathe, CNC), vacuum/instrument development lab, and main office.

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

**Site structure:** `index.html` is the main single-page site. `tools.html` and `ion-optics.html` are separate standalone pages that share its nav/footer/brand styling. No build tools, no frameworks, no npm. Pure HTML/CSS/JS throughout.

**Hosting:** GitHub Pages — free, automatic SSL via Let's Encrypt (auto-renews every 90 days).

**DNS:** GoDaddy manages GAAcustom.com. Four A records → GitHub IPs (185.199.108-111.153). CNAME www → GordonAnderson.github.io.

**Analytics:** Google Analytics G-TBTBP7GLEK (business Google account).

**Search Console:** Verified, sitemap.xml submitted.

**Price management:** All prices stored in `prices.json` in repo root. Loaded by JavaScript on page load, with fallback values hardcoded separately in **both** `index.html` and `ion-optics.html` (each standalone page carries its own copy of the price-loader script). Edit `prices.json` on GitHub for the change to show up everywhere — but also update both HTML files' fallback objects to match, since the fallback only gets overridden by `prices.json` if that fetch succeeds. See "Prices System" below for the full key list and the bug this already caused once.

**Map:** Leaflet.js with CartoDB Positron tiles (no API key, works locally and on GitHub Pages). 64 deployment locations, 16 countries. Loaded dynamically via script.onload to avoid "L is not defined" error.

---

## File Structure

```
gaacustom/
├── index.html                    ← main website
├── ion-optics.html               ← Ion Optics Components page (added July 2026)
├── tools.html                    ← free calculators for researchers
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
│     ├── ElectronicsRD.jpg       ✓ Electronics R&D lab — used in Facility gallery + About
│     ├── MassSpecs.jpg           ✓ SCIEX 6500/6600 mass specs — used in Capabilities card
│     ├── PickNplace.jpg          ✓ HW-T4-50F pick-and-place robot — used in Facility gallery (still photo) + Capabilities card
│     ├── millLath.jpg            ✓ Mill and lathe with DRO — used in Facility gallery + Capabilities card
│     ├── 3axisCNC.jpg            ✓ 3-axis CNC mill table — used in Facility gallery (still photo)
│     ├── SystemAssembly.jpg      ✓ Assembly bench with team member — used in Facility gallery
│     ├── VacuuumDevSystems.jpg   ✓ Vacuum/instrument dev lab — used in Facility gallery (note: double-u in filename)
│     ├── Office.jpg              ✓ Main office Suite 105 — used in Facility gallery
│     ├── picknplace-demo.mp4     ✓ Pick-and-place robot video — toggleable in Facility gallery (added May 2026)
│     ├── cnc-milling.mp4         ✓ 3-axis CNC milling video — toggleable in Facility gallery (added May 2026)
│     ├── dms-module.jpg          ✓ DMS Module product photo
│     ├── astraea.jpg             ✓ Astraea waveform generator (also used for ±100V driver option card)
│     ├── quad-driver-250v.jpg    ✓ Digital Quad Rod Driver ±250V
│     ├── ahmed-system.jpg        ✓ Dr. Ahmed Hamid / Auburn IMS platform (Applications section)
│     ├── fticr-preamp.jpg        ✓ FTICR Pre-Amp System product photo (added July 2026)
│     ├── ion-funnel.jpg          ✓ RF/DC Ion Funnel product photo (added July 2026)
│     ├── kf-feedthroughs.jpg     ✓ KF Feedthroughs family photo — D9/BNC/Picoblade (added July 2026)
│     └── kf-feedthroughs-installed.jpg ✓ KF Feedthroughs installed on chamber flange (added July 2026)
│
└── docs/
      ├── mips/                   ○ 16 PDFs pending upload
      ├── software/               ○ 3 PDFs pending upload
      ├── standalone/             includes FTICR_PreAmp_System.pdf ✓ (added July 2026) — several others still ○ pending upload
      ├── ion-optics/             ← NEW (July 2026) — manuals for ion-optics.html
      │     ├── Ion_Funnel_Manual.pdf         ✓
      │     └── KF_Vacuum_Feedthroughs.pdf     ✓
      └── resources/              ○ 3 PDFs pending upload
```

See README.md in the repo for complete filename list for all pending PDFs. Note: this list is reconstructed from session memory and may still lag the live repo in places (e.g. exact pending/done status of older `docs/mips/`, `docs/software/`, `docs/standalone/`, `docs/resources/` PDFs) — verify against GitHub directly when it matters.

---

## Website Sections (in order)

1. **Nav** — fixed, dark on hero / transitions to white on scroll. Logo + links + "Request Quote" CTA. CTA has `white-space:nowrap` to prevent line-break on narrow viewports. Nav links include: What We Offer, Products, Software, Applications, Testimonials, Capabilities, Facility, About, Downloads, Tools (`tools.html`), Ion Optics (`ion-optics.html`, current-page indicator uses a red bottom-border rather than color — dark nav text would be invisible against the dark default nav background), Contact.
2. **Hero** — dark background, animated grid, red glow. MIPS panel card on right.
3. **Wave divider** — SVG wave transitioning dark hero to light body.
4. **Marquee** — red scrolling strip with product names.
4a. **What We Offer** — four-column card grid between hero and Products: MIPS Ecosystem, Custom Hardware & Firmware, PCB-Level Ion Optics (links to `ion-optics.html` via a "See Ion Optics Components →" CTA added July 2026), Research Collaboration (not yet linked — awaiting `research.html`).
5. **Products** — MIPS featured card (front panel banner + home app screenshot on left; description + rear/internal tab switcher on right). Then standalone product cards with photos, in grid order: RF Generator, RF Mega, MFT, SLIM Reverser, Electrometer, FET TW Switch, DMS Module, Astraea, Astraea ±100V Driver Option, Quad Rod Driver ±250V, FTICR Pre-Amp System (added July 2026, badge "Detection"). New cards get appended at the end of the grid rather than re-sorted alphabetically — this is the established pattern.
6. **MIPS Modules accordion** — 6 collapsible categories: DC Bias, RF Driver & Heads, Waveform & Pulse, Ion Mobility & FAIMS, Specialty Voltage, Digital & System. Prices loaded from prices.json.
7. **Software Architecture** — "One Interface. Every Instrument." Light background. Inline SVG diagram showing host app → communication bus → MIPS controllers + standalone instruments → custom GUI panel. Two control panel screenshots shown side by side below diagram.
8. **Applications** — three examples so far: (1) GAACE soft landing system, (2) Prof. Brian Clowers WSU 8-meter SLIM system, (3) Dr. Ahmed Hamid Auburn IMS research platform (`ahmed-system.jpg`). Layout alternates photo left/right.
9. **Global Deployments** — Leaflet interactive map. Stats: 200+ systems, 16+ countries, 64+ institutions, 10+ years. 64 pins. CartoDB Positron tiles.
10. **Testimonials** — dark background section. Three testimonials: Dr. Brian Clowers (WSU), Prof. Ahmed Hamid (Auburn), Corentin Rossi (Institut des Sciences Moléculaires d'Orsay, Université Paris-Saclay). Rossi's was unsolicited but he has consented to public use — don't use the word "unsolicited" in any public-facing copy since the others were solicited.
11. **Capabilities** — "From Problem to Solution." 4-step process + 6 capability cards grid. Three cards (In-House Fabrication, Mass Spec Expertise, Mechanical Design) have photo headers using PickNplace.jpg, MassSpecs.jpg, millLath.jpg respectively.
12. **Facility Gallery** — "1,800 sq ft of Capability." 3 rows of facility photos/videos:
    - Row 1 (2-up large): ElectronicsRD.jpg + VacuuumDevSystems.jpg (static photos)
    - Row 2 (3-up): **SMT Assembly** card + millLath.jpg + **CNC Fabrication** card
      - SMT Assembly: shows PickNplace.jpg still photo by default; visitor clicks **"▶ Watch"** button to swap to `picknplace-demo.mp4` looping video; button changes to **"✕ Photo"** to switch back
      - CNC Fabrication: shows 3axisCNC.jpg still photo by default; same toggle behavior with `cnc-milling.mp4`
      - Toggle logic handled by `toggleVid(id)` JS function defined at the bottom of the facility section
    - Row 3 (2-up): SystemAssembly.jpg + Office.jpg (static photos)
13. **About** — company story + ElectronicsRD.jpg facility photo above team cards + team cards (Gordon, Christopher, Meri).
14. **Downloads** — accordion style, categories: MIPS System, MIPS Host Software, Standalone Instrument Manuals (now includes FTICR Pre-Amp System — added July 2026), Technical & Business. Several PDFs still not yet uploaded to GitHub but links are wired up with correct filenames.
15. **Contact** — dark background. Contact details + Google Maps embed (101904 Wiser Pkwy, Kennewick WA) + contact form (mailto: gaa@gaa-ce.com). Address updated to Suites 105 & 106.
16. **Footer** — darkest background. Links + contact info. Company column includes "Our Facility" link → `#facility`.

---

## Other Pages (not part of the index.html single-page scroll)

**`tools.html`** — free calculators for researchers: Mathieu stability diagram (Quadrupole RF/DC), Resolving Power (Quadrupole + TOF tabs), K₀/CCS Ion Mobility Converter, RF Resonant Circuit, Ion Kinetic Energy, Capacitive Load Power, Vacuum Pressure Converter, Orifice Flow/Differential Pumping, Mean Free Path. Has its own SEO meta/OG tags, a share strip (copy link, LinkedIn, X, email, citation block), and a bookmark-prompt banner. Raw HTML5 Canvas used for all calculator rendering (not Chart.js) to avoid rendering issues. `buildAQLookup()` must stay at 80 LUT entries / 800 `findPassband` scan steps — larger values (600/4000) caused severe page slowdowns.

**`ion-optics.html`** (added July 2026) — Ion Optics Components page, reusing index.html's exact `<head>` (fonts/CSS variables), nav, and footer for brand consistency. Two products live here:
- **RF/DC Ion Funnel** — $995. Specs: 4.3" standard length (custom lengths to order), 1" entrance aperture, 0.1" exit orifice, 0.04" plate spacing, 0.02" plate thickness, gold plated, ~700 pF capacitance, linear DC gradient. Driven by GAACE RF Generator/RF Mega. Manual: `docs/ion-optics/Ion_Funnel_Manual.pdf` (written from scratch — no manual existed before; content combines specs Gordon provided directly with mounting/connector details recovered from his internal assembly deck, `GAACEfunnel.pptx`).
- **PCB KF Vacuum Feedthroughs** — $35 each. KF16/KF25/KF40 flange sizes; BNC, D9, Picoblade, pin-style connectors; tested to 10⁻⁶ Torr. Manual: `docs/ion-optics/KF_Vacuum_Feedthroughs.pdf`.
- Closing "Need Something Custom?" CTA section (dark background) also name-checks planar quadrupoles, ring ion guides, and custom ion transport optics as contact-us-only capabilities (no dedicated product cards yet).
- Photos for both products were recovered from Gordon's internal PowerPoint decks (`GAACEfunnel.pptx`, `KFfeedthroughs.pptx`) rather than fresh photography — the funnel photos in particular show internal assembly labeling (RF coupling board silkscreen) rather than a styled product shot. Fine for now per Gordon, but worth swapping if cleaner product photography becomes available.
- **Nav integration:** `index.html` nav (desktop + mobile drawer) has an "Ion Optics" link styled `color:var(--red)` like the Tools link. On `ion-optics.html`'s own copy of the nav, that same link is instead styled as the "current page" indicator (`font-weight:700` + red bottom border, no color override) since the nav's default background is dark and `color:var(--ink)` would be invisible — this bug happened once already, don't reintroduce it. The homepage's "What We Offer" → "PCB-Level Ion Optics" card also links here.

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
ethernet, wifi, interlock, heater, consulting_rate, dms_module,
astraea, astraea_100v, quad_driver_250v, fticr_preamp, ion_funnel,
kf_feedthrough, kf_feedthrough_sub
```

To update: edit `prices.json` on GitHub. **Both** `index.html` and `ion-optics.html` also carry their own hardcoded JS fallback copy of every price (used if `prices.json` fails to load) — **these two fallback objects must be kept identical.** This bit already caused a live bug once: `kf_feedthrough` was updated to "$35" in `prices.json` and in `index.html`'s fallback, but `ion-optics.html`'s own embedded fallback still said "Contact for pricing" — since that script runs on page load and stamps the fallback value over the DOM *before* `prices.json` finishes fetching, the page kept showing the stale price regardless of what `prices.json` said. Whenever a price changes: update `prices.json`, `index.html`'s fallback block, and `ion-optics.html`'s fallback block, all three, every time. (If more standalone pages get added later — e.g. `research.html` — the same rule will apply to them too.)

---

## Social Media & Marketing

**LinkedIn:** Active — Gordon Anderson personal profile. First two posts performed well:
1. Website launch announcement
2. WSU SLIM system application spotlight (with Dr. Clowers photo)

**LinkedIn strategy:** Post 2-3x/month rotating: product spotlights, application examples, behind-the-scenes, customer success, technical tips, milestones. Put URLs in first comment (not post body) for better reach.

**Google Business:** Profile active. Links updated to new domain. Redirect pages handle old /about/, /capabilities/ etc. URLs.

**Content coming:** More customer lab photos, additional application notes, Research & Collaboration page content.

---

## Outstanding To-Do Items

- [ ] Upload all PDFs to docs/ folders (see README.md for filenames) — includes the two new `docs/ion-optics/` manuals and `docs/standalone/FTICR_PreAmp_System.pdf`
- [ ] Customer lab photos for Applications section (beyond Ahmed Hamid's Auburn platform)
- [ ] Module list corrections from Gordon (detailed list promised)
- [ ] GitHub MIPS software repo URL (to update 4 software download links from generic github.com/GordonAnderson to specific repo)
- [ ] Team photos (optional — currently showing initials avatars)
- [ ] More sales location data (invoices 1,036+)
- [ ] Additional application examples (FAIMS, quadrupole MS)
- [ ] **Research & Collaboration page** (`research.html`) — next planned page. Will cover two active R&D projects (low-cost modular vacuum system platform; FPGA-based TDC/TOF DAQ system), contract R&D with rate sheet, a community-input callout, and a partnership/get-involved section. Source documents not yet provided. Build following the same pattern as `ion-optics.html` (reuse index.html's head/nav/footer, own embedded price-loader fallback if it needs pricing, link from the homepage's "Research Collaboration" What We Offer card once live, add a nav link on both `index.html` and the new page itself).
- [ ] **Low-cost ion gauge** (coming soon, no specs yet) — placement depends on whether it ships with a MIPS/USB host interface (→ main standalone products grid on `index.html`, like Electrometer) or is bare hardware (→ `ion-optics.html`, like the KF feedthroughs). Ask Gordon once specs are available.
- [ ] Dedicated product treatment (specs, photos, pricing) for planar quadrupoles, ring ion guides, and other custom ion transport optics — currently just named as "contact us" capabilities in the `ion-optics.html` custom-work CTA, not yet full product entries
- [ ] Consider swapping the Ion Funnel product photos on `ion-optics.html` for cleaner product shots if/when available — the current ones were recovered from an internal assembly-instructions deck and show PCB silkscreen/labeling rather than a styled hero shot

---

## Other Project Documents

The following documents are maintained separately and used to generate the PDF Capabilities Overview:

- **Capabilities_Overview.docx** — full capabilities and resources document with embedded facility photos (5 photos: ElectronicsRD, PickNplace, millLath, MassSpecs, SystemAssembly). Generated with docx-js. Source build script: `build_capabilities.js`.
- **RateSheet03292026.docx** — current rate sheet
- **Warranty_Statement.docx** — warranty policy document

---

## How to Update the Site

**For content/design changes:**
1. Paste this document + index.html into a new Claude chat
2. Describe what you want changed
3. Claude outputs updated index.html
4. Upload to GitHub (drag over existing file → Commit)
5. Live in ~60 seconds

**For price changes:**
Edit `prices.json` on GitHub, **and** update the matching fallback value in both `index.html` and `ion-optics.html` (search each file for `var fallback = {`). Skipping the fallback update is what caused the `kf_feedthrough` price to look "stuck" once already — see Prices System above.

**For new photos:**
Upload photo here in chat → Claude adds to index.html with correct img tag → upload both index.html and the photo to GitHub in the `images/` folder

**For new videos:**
Convert iPhone .MOV to .MP4 (rename extension or use FreeConvert.com to compress), place in `images/` folder on GitHub. Reference as `images/filename.mp4` in a `<video>` element. See the facility gallery toggle pattern for how to pair a still photo with a video.

**For new PDFs:**
Rename to exact filename from README.md → upload to correct docs/ subfolder on GitHub → download link goes live automatically, no HTML change needed

**For new map locations:**
Provide city/state or city/country list → Claude adds pins to the Leaflet locations array

**For new testimonials:**
Provide quote text, name, title, institution, and optionally a profile URL → Claude adds a new card to the Testimonials section

**For Capabilities_Overview.docx updates:**
Paste this document + build_capabilities.js into a new Claude chat → describe changes → Claude regenerates the .docx

---

## Important Notes for Claude

- The site uses **data-price** attributes on all price elements — never hardcode prices directly in HTML, always use `<span data-price="key">fallback</span>` format and add the key to prices.json
- The Leaflet map script uses `script.onload` pattern — never call L.map() outside the `initDeployMap()` function
- The nav color transition (dark over hero → white on scroll) uses `nav.classList.toggle('scrolled', window.scrollY > 80)` — preserve this
- The MIPS featured card left panel uses flexbox column layout with front panel banner on top and mips-home.jpg below — don't revert to the old fixed-height layout
- All external links (GitHub, Google Maps, WSU faculty pages) use `target="_blank"`
- The `toggleDL()` function handles the downloads accordion, `toggleCat()` handles the modules accordion, `toggleVid(id)` handles the photo/video swap in the facility gallery — all three must be preserved
- `toggleVid(id)` uses element IDs in the pattern `{id}-img`, `{id}-vid`, `{id}-btn` (e.g. `pnp-img`, `pnp-vid`, `pnp-btn` for pick-and-place; `cnc-img`, `cnc-vid`, `cnc-btn` for CNC). Follow this pattern for any additional video toggles.
- Google Analytics ID: G-TBTBP7GLEK — already in the `<head>`
- Favicon tags already in `<head>` referencing `favicons/` folder
- Open Graph tags already in `<head>` referencing `images/og-preview.jpg`
- Sitemap reference already in `<head>`
- **Facility section** (`id="facility"`) sits between Capabilities and About — preserve this order
- **VacuuumDevSystems.jpg** has a double-u typo in the filename — this matches what is referenced in index.html, do not "correct" it or the image will break
- Address is **Suites 105 & 106** throughout — the facility occupies two attached units
- Videos in the facility gallery are **not autoplay** — they only play when the visitor clicks "▶ Watch". Do not add autoplay to facility video elements.
- **Photos from Gordon's iPhone can come out washed out/desaturated on the web** even though they look fine in macOS Preview. Cause: the photo has an embedded wide-gamut color profile (seen so far: "Display P3 Primaries"), and browsers that don't color-manage it read the raw values as if they were plain sRGB — which under-saturates them, since P3 is a wider gamut. This is *not* fixable by boosting contrast/saturation with a blind PIL `ImageEnhance` pass (tried once, didn't help, because it also strips the profile without doing the actual color conversion — same mismatch, just less visible on the surface). The correct fix: read the embedded ICC profile and do an actual colorimetric conversion to sRGB, e.g. with Pillow's `ImageCms.profileToProfile(img, source_profile, srgb_profile)`, then save without an ICC tag (the pixel values are now genuinely sRGB, so no tag is needed). Gordon's own workaround — opening the photo in PowerPoint and re-saving — works for the same underlying reason: PowerPoint flattens the image to plain sRGB during that round-trip. Check `img.info.get('icc_profile')` before assuming a "washed out" photo just needs a contrast tweak.
- **`ion-optics.html` (and any future standalone page like it) carries its own copy of the price-loader `<script>` block, with its own hardcoded fallback object** — it is not shared with `index.html`. Any time a price changes, update `prices.json` **and** both HTML files' fallback objects, or the standalone page will silently keep showing the old value even after `prices.json` is correct (this already happened once with `kf_feedthrough`). Quick way to check they match: diff the `var fallback = {...}` block between the two files.
- When building a new standalone page that shares the site's chrome (like `ion-optics.html`), reuse `index.html`'s nav and footer blocks verbatim rather than rewriting them, but rewrite every in-page anchor href (`#products`, `#about`, `#contact`, etc.) to `index.html#products`, `index.html#about`, etc. — a bare `#anchor` href on a different physical page just scrolls nowhere. Also point the nav logo at `index.html` instead of `#`.
- The site's nav is **dark by default** (it's designed to sit over the dark hero on `index.html`) and only becomes light after `nav.classList.toggle('scrolled', ...)` fires on scroll. A "current page" nav-link indicator on a standalone page must not set `color:var(--ink)` (near-black) — that's invisible against the dark default nav and the dark mobile drawer. Use something color-agnostic instead, like a red bottom border plus bold weight, so it stays visible in both the dark and scrolled states.
