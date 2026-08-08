# GAA Custom Electronics — Website Development Handoff
## Context Document for Claude AI Sessions

Paste this document along with `index.html` at the start of any new Claude chat session to resume website development without losing context.

**Last substantive update:** July 2026 — added the "Open by Design" fifth pillar to `index.html`, and built two new pages: `research.html` and `open-source.html`. See **Open Source Position** below — that section is accuracy-critical and has already been corrected twice.

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

## SLIM / MOBILion — Naming and Attribution (July 2026)

**Product rename applied.** The "SLIM Reverser" is now the **"Twave Reverser"** everywhere reader-facing on index.html: product card, marquee, downloads row, contact dropdown, footer link. Rationale: the product is a general-purpose 16-pole traveling-wave signal-order switch, applicable to any Twave device — not specific to SLIM. Gordon's MIPS manual and the reverser deck already used TWAVE terminology, so this aligns naming with existing docs. The rename predates the current MOBILion sensitivity (the deck was already half-renamed), which is worth remembering: it's an accuracy decision, not a reaction.

**Price key renamed:** `slim_reverser` → `twave_reverser`. Updated in BOTH `prices.json` and the index.html JS fallback (value unchanged, $395). ion-optics.html has no fallback for this key (product not on that page), so the usual three-file sync was two files here. **Verify ion-optics.html on GitHub doesn't reference the old key before deploying.**

**Manual:** downloads link now points to `docs/standalone/TWAVE_Reverser.pdf`. Gordon must place the renamed PDF (from the TWAVErev4_0 deck) at that path, and should keep `docs/standalone/SLIM_Reverser.pdf` working as a copy so existing bookmarks don't 404.

**Product-card image** `images/slim-reverser.jpg` was NOT renamed (alt text was). Renaming an image path requires renaming the repo file in lockstep or the card breaks — same caution as the deliberate `VacuuumDevSystems.jpg` typo. Rename the file first, then update the reference if desired.

**SLIM deliberately KEPT where factual:** WSU application (Brian Clowers' 8-meter system), Auburn testimonial, meta/SEO tags, and "supports SLIM" capability text on Twave products. SLIM is a real search term and these statements are accurate. Do not scrub these.

**MOBILion spotlight added** to the Applications ("MIPS in the Lab") section, after the Hamid entry, photo-left. Title: "SLIM*-QTOF Platform Enabling PAMAF™ Proteomics — MOBILion Systems." Content is MOBILion's own write-up (from Daniel DeBord, CTO), published with permission, with an attribution line. Photo path: `images/mobilion-slim-qtof.jpg` — **Gordon still needs to place this file** (currently only have a 695×603 downscaled version; ask MOBILion for full-res). Links out to mobilionsystems.com, their PAMAF news page, and their SLIM technology page.

**SLIM licensing footnote** added at the end of the Applications section (`id="slim-note"`). Both SLIM asterisks (WSU heading + MOBILion heading) link to it. Contains MOBILion's requested exclusive-licensee statement verbatim plus a trademark line. Single footnote covers the whole page (single-scroll).

**IMPORTANT context — legal sensitivity.** There is tension around SLIM IP. MOBILion has reportedly pressured Brian Clowers (WSU) and complained to PNNL about infringement, alleging GAACE electronics enable IP violation — though this is secondhand via Brian, and MOBILion has said nothing directly to Gordon. Separately, MOBILion's CTO sent Gordon the spotlight write-up and photo and asked him to post the licensee statement — a cordial, direct interaction. GAACE's reverser electronics that predate MOBILion's existence are a strong position (can't circumvent a license that didn't exist); the reverser itself is more recent. **Gordon is advised to have a patent attorney review before publishing the MOBILion material and before the open hardware release, and to preserve all correspondence.** Do not draft legal reasoning into emails. The rename + footnote + spotlight are staged in outputs but should not go live until Gordon has had that review and heard back from Daniel on the photo.

---

## Open Source Position — ACCURACY CRITICAL

Added July 2026. This is GAACE's strongest differentiator — no other electronics supplier in mass spectrometry publishes comparably. It is also the easiest thing in this project to overstate, and AI-drafted copy has already had to be corrected **twice** for exactly that. Read this section before writing any open-source copy.

### The accurate framing — three distinct layers

1. **Software** — MIPS controller firmware and the Qt host application have been public on GitHub **since the company started**. No request needed, nothing gated.
2. **Hardware** — being published on GitHub **progressively**. Not complete. The plan is to start with discrete, self-contained designs (vacuum feedthroughs, PCB ion optics) and work outward toward more complex assemblies and eventually full systems.
3. **Design data on request** — GAACE shares technical data directly with researchers who ask: a schematic for a board someone is troubleshooting, design files to base a variant on, whatever the work actually requires. Free, no NDA.

**Framing matters here (third correction, July 2026).** Do *not* describe this as a "complete technical data package available on request." That wording implies a finished, shelf-ready deliverable, and Gordon's concern is that it would generate requests he isn't yet in a position to fill. The site now uses **request-driven** language instead — *"if there's technical data you need, ask us"* — which makes the same openness point while leaving room to assemble the full design library over time. Related: the checklist on `open-source.html` is headed **"Design Data We Can Share"** (not "What's In A Technical Data Package"), and its items were softened away from absolutes — "Schematics, in PDF or native CAD format" rather than "Full schematics, per module"; "Bills of material with vendor part numbers" rather than "Complete bill of materials with live vendor part links."

The hero stat block changed for the same reason: **"Free / Tech Data, On Request"** → **"No / NDA Required."**

### Do NOT write

- ❌ **"Every system ships with its complete engineering package."** Tech data is provided *on request*, not automatically bundled. This was the first correction.
- ❌ **"Complete technical data packages are available to any customer who wants one."** Implies a ready-made deliverable that doesn't exist yet. Use request-driven language instead. This was the third correction — see the note under layer 3 above.
- ❌ **Any specific completion date.** A "by 2030, anyone skilled in the art could build one of our systems" commitment was drafted, built out into a full page section with a dated roadmap, and then **deliberately removed at Gordon's direction**. The long-range goal is real but is stated *without* a date. The page says: *"We're not putting a date on that, because we'd rather publish it properly than publish it fast."* This was the second correction.
- ❌ Absolute claims such as "nothing we build is a black box."
- ❌ Calling it OSI "open source" without qualification in legal/licensing contexts — see below.

**General principle across all three corrections:** every error has been in the direction of promising more readiness than exists. The openness is genuine; the *packaging* of it is still being built. When in doubt, describe the intent and the direction, not a finished artifact.

### Roadmap framing currently on `open-source.html`

Three cards, no dates:
- **Established** — software, public since the start
- **Underway** — discrete hardware, starting simple; also building the repository structure and documentation practices that more complex releases will depend on
- **Ahead** — toward full systems; long-range aim of a public design library complete enough to build from

The honest engineering argument the page makes for why hardware is slower than code: design files written for your own bench aren't self-explanatory to a stranger, and a folder of Gerbers isn't the same thing as something someone can actually build. Doing it properly means consistent file formats, revision discipline, parts lists that stay current, and assembly notes written for someone who has never seen the board.

### Licensing — RESOLVED July 2026

Gordon chose genuinely open licenses rather than the earlier source-available framing. The old "we ask that you don't manufacture for commercial resale" language has been **removed from the site** — it contradicted the licenses now in use.

| Asset | License | SPDX |
|---|---|---|
| Hardware design files | CERN Open Hardware Licence v2 — Weakly Reciprocal | `CERN-OHL-W-2.0` |
| Firmware (runs on GAACE boards) | MIT License | `MIT` |
| Host application / portable software | GNU General Public License v3.0 or later | `GPL-3.0-or-later` |
| Documentation | Creative Commons Attribution 4.0 | `CC-BY-4.0` |

**Firmware/host-app split (decided July 2026, updated from an earlier firmware=GPL choice).** Firmware is **MIT**: it only runs on GAACE hardware, so copyleft buys little, and MIT stays compatible with the mostly-MIT/LGPL Arduino/ARM library ecosystem. The host application (MIPS_QT6) is **GPL-3.0**: it's portable, so it's where a closed competing fork could matter. This is the standard open-hardware split. Note the one-way-door rule: MIT→GPL is easy, GPL→MIT is not, so MIT was the safe default for firmware. The licensing kit reflects this with three repo templates: `hardware-repo/` (CERN-OHL-W), `firmware-repo/` (MIT), `hostapp-repo/` (GPL-3.0).

**Why OHL-W rather than OHL-S:** weakly reciprocal means someone distributing a product based on a *modified* GAACE design must publish their modified design files, but does **not** have to open the surrounding product. That keeps the door open for OEM customers (Bruker, Thermo, Agilent) to embed GAACE hardware in proprietary instruments. OHL-S would have barred that.

**Trademark, not license, is the actual protection.** "GAA Custom Electronics," "GAACE," "MIPS," and "Astraea" are reserved in every template and on the site. Someone may build the board; they may not call it a MIPS module. This is the Arduino/Adafruit model. Filing for MIPS and Astraea is on the pre-publish checklist.

**Customer-funded work is carved out explicitly.** Custom development funded by a customer belongs to that customer, is typically under NDA, and is never published. Where GAACE funds the work itself — including upgrades that began as a customer request — the result is GAACE's and goes out under the licenses above. This is stated in a callout in the `open-source.html` Terms section.

**A full licensing kit was generated** (delivered as `gaace-licensing-kit.zip`, 21 files): drop-in `hardware-repo/` and `firmware-repo/` folders with verbatim SPDX license texts, README and CONTRIBUTING templates, a profile README for `GordonAnderson/GordonAnderson`, a canonical `licensing` repo README, SPDX header snippets, a CERN-OHL Source Location notice, a filled-in example README for the feedthroughs, and a pre-publish checklist.

**Contributor terms:** the CONTRIBUTING templates use a **forward-license grant** (contributions may be distributed under the current license *or any later license the project adopts*) plus **DCO sign-off** rather than a full CLA. Rationale: GAACE currently owns 100% of the copyright and can relicense freely; that ends at the first merged pull request unless contributors agree up front. A CLA would preserve more flexibility but adds friction that academic contributors often can't clear quickly.

**Still open:** `RateSheet03292026.docx` says product IP is "nontransferable" and cannot be "duplicated, transferred and/or re-sold." That directly contradicts an open hardware license. Scope the clause to customer-funded proprietary work, or update it. Also unresolved: whether GPL-3.0 is the right choice for Arduino/ARM firmware given library compatibility (many Arduino libraries are MIT or LGPL-2.1; a GPL-2.0-only library would be incompatible, and vendor HALs with "use only with our chips" clauses are a known problem). Splitting — MIT for firmware, GPL-3.0 for the Qt host app — is worth considering.

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

**Site structure:** `index.html` is the main single-page site. `tools.html`, `ion-optics.html`, `research.html`, and `open-source.html` are separate standalone pages that share its nav/footer/brand styling. No build tools, no frameworks, no npm. Pure HTML/CSS/JS throughout.

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
├── research.html                 ← R&D programs / collaboration / rates (added July 2026)
├── open-source.html              ← open hardware & firmware practice (added July 2026)
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

1. **Nav** — fixed, dark on hero / transitions to white on scroll. Logo + links + "Request Quote" CTA. CTA has `white-space:nowrap` to prevent line-break on narrow viewports. Nav links include: What We Offer, Products, Software, Applications, Testimonials, Capabilities, Facility, About, Downloads, Tools (`tools.html`), Ion Optics (`ion-optics.html`), Open Source (`open-source.html`), Research (`research.html`), Contact. Current-page indicators use a red bottom-border + `font-weight:700` rather than a color change — dark nav text would be invisible against the dark default nav background.

**Nav crowding (July 2026):** the desktop nav is now at 11 items plus the "Request Quote" CTA button. It fits, but below the 1100px breakpoint the links shrink to `.74rem` and it's visibly tight. To make room, the desktop nav on `research.html` and `open-source.html` **omits "Capabilities"** — it is still present in their mobile drawers and footers. `index.html` still shows it. **This is an unresolved inconsistency; decide whether index should match.** Longer term this may want dropdowns, or folding Applications/Capabilities into About.
2. **Hero** — dark background, animated grid, red glow. MIPS panel card on right.
3. **Wave divider** — SVG wave transitioning dark hero to light body.
4. **Marquee** — red scrolling strip with product names.
4a. **What We Offer** — heading is **"Five Ways We Support Your Research."** Four-column card grid between hero and Products: MIPS Ecosystem, Custom Hardware & Firmware, PCB-Level Ion Optics (links to `ion-optics.html` via a "See Ion Optics Components →" CTA added July 2026), Research Collaboration. Below those, a **fifth full-width pillar: "Open by Design"** (added July 2026) using the `.offer-cell-wide` class — `grid-column:1/-1` with a dark background so it reads as *the* differentiator rather than a fourth peer. Contains the open-source summary, a tag list of what's in a technical data package, and an "Our Open Source Practice →" link to `open-source.html`. See **Open Source Position** above before editing its copy.
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

**`research.html`** (added July 2026) — R&D programs, collaboration, and contract rates. Reuses `index.html`'s head/nav/footer pattern. **No price elements** — the rates table is plain HTML, deliberately not wired to `prices.json`, so this page does *not* need a price-loader fallback block. Sections in order:
- Hero — *"What we're building next."* Stats: 4 Active Programs / 2014 Established / 16+ Countries Served
- **Active Research Programs** — four numbered blocks using the `.prog` grid: (1) Low-Cost Modular Vacuum Platform *(prototype operational)*, (2) FPGA Time-to-Digital Converter & TOF Data Acquisition *(active development)*, (3) Low-Cost Ion Gauge *(in development)*, (4) Planar Quadrupoles & Ring Ion Guides *(shipping, expanding)* — this last one cross-links to `ion-optics.html`. Each has a `.spec` tag row.
- Compact dark cross-link strip → `open-source.html`
- **Four Ways to Collaborate** — free design consultation, contract development, research partnerships, SBIR/STTR co-proposing. Plus a "Tell us what to build next" callout.
- **Contract R&D rates** — $140/hr (half-hour increments, 1 hr min), $1,120/day, $5,600/week, first 30 min free, travel/materials at cost +10%, net 30. Links to the rate sheet in the downloads section.
- CTA — primary action is **Contact Us**
- **Pending from Gordon:** photos and expanded detail for all four research programs.

**`open-source.html`** (added July 2026) — the open hardware/firmware practice. **No price elements.** Sections in order:
- Hero — H1 is the literal phrase **"Open source mass spectrometry hardware."** Stats: 2014 Publishing Code Since / Free Tech Data On Request / 64+ Institutions Deployed
- **Why We Publish Everything** — three arguments (experiments outlive documentation; reproducibility requires disclosure; vendor risk is real) alongside a "What's In A Technical Data Package" checklist
- **Where This Is Headed** — the undated Established / Underway / Ahead roadmap
- **Public Repositories** — `GordonAnderson`, `MIPS-Resources`, `MIPS_QT6`, `gaacustom`, plus a contributing card
- **What Open Means Here** — licensing terms (see Open Source Position above; unresolved)
- CTA — primary action is **Browse the Repositories**

**Why `research.html` and `open-source.html` are two pages, not one.** They were originally drafted as a single `research.html`. Split at Gordon's direction because: the open-release material grew past section size; the research programs are about to expand substantially with photos and depth; a page named "Research" was leading with open-source content, which is a name/content mismatch; each page now has one clear call to action (Open Source → "browse the repos", Research → "contact us"); and "open source mass spectrometry hardware" is an essentially uncontested search phrase that now owns its own page title, H1, meta description, canonical, and OG tags. **Do not re-merge them.**

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

To update: edit `prices.json` on GitHub. **Both** `index.html` and `ion-optics.html` also carry their own hardcoded JS fallback copy of every price (used if `prices.json` fails to load) — **these two fallback objects must be kept identical.** This bit already caused a live bug once: `kf_feedthrough` was updated to "$35" in `prices.json` and in `index.html`'s fallback, but `ion-optics.html`'s own embedded fallback still said "Contact for pricing" — since that script runs on page load and stamps the fallback value over the DOM *before* `prices.json` finishes fetching, the page kept showing the stale price regardless of what `prices.json` said. Whenever a price changes: update `prices.json`, `index.html`'s fallback block, and `ion-optics.html`'s fallback block, all three, every time. (The same rule applies to any future standalone page that displays prices. Note that `research.html` and `open-source.html`, added July 2026, deliberately carry **no** `data-price` elements and therefore no fallback block — the contract R&D rate table on `research.html` is plain HTML. If prices are ever added to either page, they must join the sync list.)

---

## Social Media & Marketing

**LinkedIn — personal profile:** Gordon Anderson. First two posts performed well:
1. Website launch announcement
2. WSU SLIM system application spotlight (with Dr. Clowers photo)

**LinkedIn — Company Page:** `linkedin.com/company/gaa-custom-electronics` (ID 142889387). Established 2026. **7 followers as of July 2026 — follower growth, not content, is the actual bottleneck.**

Page state as of July 2026:
- ✓ Cover image is good — three real products, no stock photography, legible to someone who knows the field
- ✓ Overview is well-organized and concrete (MIPS description, four offering bullets, team, location)
- ✗ **Logo has an opaque white box** behind the circular mark, so it reads as a sticker on the dark cover. Re-export at 400×400 with a transparent background, or scale the circle to fill the frame.
- ✗ **No custom button set** — should be "Visit website" → `https://www.gaacustom.com`. Currently the only action is "Message," which is a higher-commitment ask.
- ✗ **Overview does not mention the open-hardware position.** A revised version was drafted that moves it into the first paragraph — LinkedIn truncates at roughly three lines, and the currently-visible portion is generic enough to describe a competitor.
- ✗ **Specialties missing** `Open Hardware` and `Open Source Firmware` — searchable terms with essentially no competition
- ✗ **Only 1 associated member** — Christopher and Meri should list GAACE as employer on their personal profiles, which also populates the empty People tab
- ✗ **Posts tab is empty**

**Posting strategy:** personal account for major announcements (much larger reach); Company Page for incremental updates. Niche B2B scientific audience — focused single-topic announcements outperform diluted multi-topic posts. Short and punchy preferred.

**Mechanics learned:**
- There is **no way to post to a Company Page without it also reaching followers' feeds.** Targeted updates exist (filter by location, industry, job function, company size) but require **300+ followers**.
- **Pinning:** Company Pages can pin a post to the top via the post's "…" menu. Personal profiles use the **Featured** section instead. Pinning also extends a Page post past the normal 1-year / 500-post admin retention limit.
- LinkedIn auto-shortens URLs to `lnkd.in` — normal and unavoidable
- **Upload the photo before pasting URL text**, or the link preview card displaces the photo button
- A post with no image gets substantially less reach
- "Another admin" error on new Company Pages is a known caching glitch — hard refresh or incognito resolves it
- Tag collaborators confidently when they have an active presence; verify sparse profiles before tagging

**Planned posts (not yet published — see To-Do):** two separate posts, one on open source and one on research. Sequenced apart by a week or two, not back-to-back. **Both wait until at least one hardware release is live on GitHub** — an interested reader's first action is clicking through, and an empty repo undoes the post.

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
- [x] ~~**Research & Collaboration page** (`research.html`)~~ — **built July 2026**, and split into two pages (`research.html` + `open-source.html`). See "Other Pages" above. **Not yet deployed to GitHub.**

### Immediate sequence Gordon has set (July 2026)

1. Read through `research.html` and `open-source.html` carefully
2. **Add photos and depth to the four research programs** — pending from Gordon
3. **Perform one hardware release to GitHub** — feedthroughs first, as the simplest self-contained design
4. *Then* post to LinkedIn — two separate posts, one open-source and one research

**The first hardware release sets the template.** Whatever folder layout, revision naming, Gerber-vs-native-CAD organization, README structure, and BOM format the feedthrough repo uses becomes the pattern for every release after it. Worth deciding deliberately once — retrofitting across a dozen repos later is painful.

### New items from the July 2026 session

- [ ] **`LICENSE` file** — see "Open Source Position" above. Nothing exists yet. Needed before or alongside the first hardware release.
- [ ] **"What's published so far" list on `open-source.html`** — a short, updated list of which designs are actually up. This is the mechanism that makes progress visible now that there is deliberately no target date attached. Without it, a visitor a year from now has no way to tell whether anything happened.
- [ ] **Nav consistency** — "Capabilities" appears in `index.html`'s desktop nav but was dropped from `research.html` and `open-source.html` to control crowding. Decide whether index should match.
- [ ] **LinkedIn Company Page fixes** — logo transparency, custom button, revised Overview with the open-hardware position in the first paragraph, add Open Hardware / Open Source Firmware to Specialties, Chris and Meri to list GAACE as employer. See Social Media section.
- [ ] **SEO** — keyword list from an earlier wordcloud exercise is available for use. `open-source.html` is already targeted at "open source mass spectrometry hardware," which has essentially no competition.
- [ ] Deploy `index.html`, `research.html`, and `open-source.html` to GitHub — **all three are built but not yet live.**
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
- **Before writing any open-source or open-hardware copy, read the "Open Source Position" section above.** It has a specific "do NOT write" list. Two overclaiming errors have already been made and corrected: (1) stating that technical data packages ship automatically with every system — they are provided *on request*; (2) attaching a "by 2030" completion date to the full-public-release goal — the goal is real, the date was deliberately removed. **When in doubt, understate.**
- **Gordon has deep domain expertise in quadrupole mass spectrometry physics and will catch conceptual errors. Defer to his corrections on physics.** Known specifics: in quadrupoles only the **DC voltage** changes to adjust resolution (RF is fixed for a given m/z); "unit resolution" is instrument-dependent, not a fixed a/q value; practical resolving-power benchmarks differ substantially from Dawson theoretical limits, so `tools.html` uses a dual-benchmark design with the practical limit as the default.
- **Gordon evaluates new features for audience fit before committing effort** — e.g. a proposed word cloud was rejected as low-credibility for a technical academic audience. Don't assume a capability is worth building just because it's available.
- **Editing method:** surgical `str_replace` against unique anchor strings, never full-file rewrites. Verify the match count is exactly 1 before replacing. Working file flow: copy from `/mnt/user-data/uploads/` → edit in `/home/claude/` → deliver to `/mnt/user-data/outputs/`.
- **The authoritative source for `index.html` is the live GitHub repo**, not any cached project file or prior session output. When in doubt, download fresh from GitHub before editing.
- **`research.html` and `open-source.html` share a full standalone `<style>` block** that duplicates the design tokens rather than importing them. Both carry the complete CSS including classes only one of them uses (`.road`, `.prog`, `.repo`, `.rate-table`). This is deliberate — it keeps each page self-contained and matches the `ion-optics.html` pattern — but it means a design-token change must be applied to every page that carries a copy.
- **`build_capabilities.js`** (for Capabilities_Overview.docx) uses the `docx` npm library. **Avoid `PageNumber` / `PageNumberElement` exports — they cause validation failures.**
- **Business codes** (for university vendor portals): Primary NAICS 334515, secondary 334516, UNSPSC 41112200 (lead with this one in vendor portals), FSC/PSC 6625.
- **Google Scholar:** `https://scholar.google.com/citations?hl=en&user=u2xMtMgAAAAJ&view_op=list_works&sortby=pubdate` — linked from the site as publication credibility.
- **Update this document at the end of any session with significant changes.** It is the only continuity mechanism between sessions.
