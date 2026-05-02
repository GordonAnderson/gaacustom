# GAA Custom Electronics, LLC — Website

Official website for **GAA Custom Electronics, LLC** (GAACE), Kennewick, WA.

**Live site:** [www.GAAcustom.com](http://www.GAAcustom.com)  
**GitHub Pages:** [GordonAnderson.github.io/gaacustom](https://GordonAnderson.github.io/gaacustom)

---

## About GAACE

GAA Custom Electronics develops custom electronics monitoring and control systems for mass spectrometry research. Our flagship product, **MIPS** (Modular Intelligent Power Sources), is deployed at universities, national laboratories, pharmaceutical companies, and instrument manufacturers in 16+ countries.

- Founded 2014 · Kennewick, WA · 509.628.6851
- 200+ MIPS systems deployed globally
- Open-source hardware and software

---

## Complete File Structure & Roadmap

Use this as a checklist — add files as they become available. Links on the website are already wired up; files appear automatically when placed in the correct location with the exact filename shown.

```
gaacustom/
│
├── index.html                          ← Main website (single-page, do not rename)
├── README.md                           ← This file
│
├── images/                             ← All photos and graphics
│     ├── logo.jpeg                     ✓ Done
│     ├── mips-front.jpg                ✓ Done
│     ├── mips-rear.jpg                 ✓ Done
│     ├── mips-internal.jpg             ✓ Done
│     ├── mips-home.jpg                 ✓ Done — MIPS host app screenshot
│     ├── rf-generator.jpg              ✓ Done
│     ├── rf-mega.jpg                   ✓ Done
│     ├── mft.jpg                       ✓ Done
│     ├── slim-reverser.jpg             ✓ Done
│     ├── electrometer.jpg              ✓ Done
│     ├── fet-switch.jpg                ✓ Done
│     ├── control-panel-1.jpg           ✓ Done — 2 RF 24 DCbias 1 ESI panel
│     ├── control-panel-2.jpg           ✓ Done — 2 RF 16 DCbias Astraea panel
│     ├── soft-landing.jpg              ✓ Done — soft landing research system
│     ├── lab-facility.jpg              ○ Pending — lab/workspace photo
│     └── team.jpg                      ○ Pending — team photo (optional)
│
└── docs/
      │
      ├── mips/                         ← MIPS system & module manuals
      │     ├── MIPS_Operations_Manual.pdf              ✓ Done
      │     ├── ARB_Module.pdf                          ✓ Done
      │     ├── Quad_Module.pdf                         ✓ Done
      │     ├── DCbias_Switch_Module.pdf                ✓ Done
      │     ├── DCbias_Analog_Control_Module.pdf        ✓ Done
      │     ├── DCbias_Output_Current_Monitor.pdf       ✓ Done
      │     ├── FAIMS_Module.pdf                        ✓ Done
      │     ├── Level_Detection_Module.pdf              ✓ Done
      │     ├── Filament_Module.pdf                     ✓ Done
      │     ├── FPGA_Module.pdf                         ✓ Done
      │     ├── RF_Head_Calibration.pdf                 ✓ Done
      │     ├── Ultra_RF_High_Q_Head.pdf                ✓ Done
      │     ├── RF_Gating.pdf                           ✓ Done
      │     ├── Multiple_Tables.pdf                     ✓ Done
      │     ├── ADC_Change_Detection.pdf                ✓ Done
      │     └── Delayed_Triggering.pdf                  ✓ Done
      │
      ├── software/                     ← MIPS host software docs
      │     ├── MIPS_User_Manual.pdf                    ✓ Done
      │     ├── Timing_Generator.pdf                    ✓ Done
      │     └── Pulse_Sequence_Generation.pdf           ✓ Done
      │     (Example config files and software download → GitHub links)
      │
      ├── standalone/                   ← Standalone instrument manuals
      │     ├── Electrometer.pdf                        ✓ Done
      │     ├── FAIMS_Rectangular_Waveform_Generator.pdf ○ Pending
      │     ├── FET_Pulsers.pdf                         ○ Pending
      │     ├── FET_Switch.pdf                          ○ Pending
      │     ├── MFT.pdf                                 ✓ Done
      │     ├── RF_Generator.pdf                        ✓ Done
      │     ├── RF_Mega.pdf                             ✓ Done
      │     └── SLIM_Reverser.pdf                       ✓ Done
      │
      └── resources/                    ← Business & technical documents
            ├── Rate_Sheet.pdf                          ✓ Done
            ├── Warranty_Statement.pdf                  ✓ Done
            └── Capabilities_Overview.pdf               ○ Pending
```

**Legend:**
- `✓ Done` — file is in the repository and live on the site
- `○ Pending` — file linked on website, will appear automatically when uploaded

---

## Important File Naming Rules

- **No version numbers in filenames** — when a document is revised, upload the new version with the **same filename**. The website link stays the same and visitors always get the latest version.
- **Filenames are case-sensitive** — use exactly the names shown above, including underscores and capitalization.
- **No spaces in filenames** — use underscores instead.

---

## Updating the Site

### Content changes (text, prices, new sections)
1. Describe the change in the Claude chat session
2. Download the updated `index.html`
3. Upload to GitHub (drag and drop over the existing file → Commit changes)
4. Live within ~60 seconds

### Adding or updating a document
1. Rename your PDF to match the exact filename in the structure above
2. Go to the correct folder in this repository (`docs/mips/`, `docs/standalone/`, etc.)
3. Click **Add file → Upload files** → drag in the PDF → **Commit changes**
4. The download link on the website is already active — no HTML change needed

### Adding a new document not yet listed
1. Tell Claude what the document is and what folder it belongs in
2. Claude will add the download entry to the site and give you the exact filename to use
3. Upload the PDF with that filename

### Adding or updating a photo
1. Name the photo using the exact filename from the `images/` list above
2. Go to the `images/` folder in this repository
3. Upload the file (same name = automatic replacement, no HTML change needed)
4. New photo? Tell Claude and it will be added to the site

---

## Website Sections

The single-page site is organized as follows:

| Section | Content |
|---------|---------|
| Hero | Dark intro with MIPS hero panel |
| Products | MIPS featured card + module accordion + standalone products |
| Software Architecture | One Interface diagram + control panel examples |
| Applications | Soft landing system + more examples coming |
| Global Deployments | Interactive Leaflet map — 64+ locations, 16+ countries |
| Capabilities | How we work + engineering capabilities |
| About | Company story + team (Gordon, Christopher, Meri) |
| Downloads | Accordion — MIPS manuals, software, standalone, resources |
| Contact | Contact form + facility map (Kennewick, WA) |

---

## Content Still Needed

- [ ] Customer testimonials (emailed to select customers)
- [ ] Customer lab photos showing MIPS in use
- [ ] Additional application examples (ion mobility, FAIMS, quad MS)
- [ ] Lab/facility photo for About section
- [ ] GitHub MIPS software repository URL (to update software download links)
- [ ] MIPS module list corrections and additions
- [ ] More sales locations (invoices 1,036+)

---

## Technical Notes

- **Hosting:** GitHub Pages — free, fast, global CDN
- **Map tiles:** CartoDB Positron (free, no API key, works locally and on GitHub Pages)
- **Fonts:** DM Sans, DM Mono, Fraunces — loaded from Google Fonts
- **No dependencies:** No build tools, no npm, no frameworks — pure HTML/CSS/JS
- **Leaflet.js:** Loaded dynamically from CDN for the deployment map

---

## Domain

**GAAcustom.com** is registered via GoDaddy.  
DNS configured with GitHub Pages IP addresses and CNAME → `GordonAnderson.github.io`

---

## Contact

**GAA Custom Electronics, LLC**  
101904 Wiser Pkwy, Suite 105  
Kennewick, WA 99338  

📞 509.628.6851  
✉️ gaa@gaa-ce.com  
🌐 www.GAAcustom.com

---

*Website developed and maintained with AI assistance via Claude (Anthropic).*
