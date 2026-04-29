# GAA Custom Electronics, LLC — Website

Official website for **GAA Custom Electronics, LLC** (GAACE), Kennewick, WA.

**Live site:** [www.GAAcustom.com](http://www.GAAcustom.com)

---

## About GAACE

GAA Custom Electronics develops custom electronics monitoring and control systems for mass spectrometry research. Our flagship product, **MIPS** (Modular Intelligent Power Sources), is deployed at universities, national labs, and instrument companies worldwide.

- Founded 2014 · Kennewick, WA
- 200+ MIPS systems deployed globally
- Open-source hardware and software

---

## Repository Structure

```
gaacustom/
├── index.html              ← Main website (single-page)
├── README.md               ← This file
│
├── images/                 ← All photos and graphics
│     ├── logo.jpeg
│     ├── mips-front.jpg
│     ├── mips-rear.jpg
│     ├── mips-modules.jpg
│     ├── rf-generator.jpg
│     ├── rf-mega.jpg
│     ├── mft.jpg
│     ├── slim-reverser.jpg
│     ├── electrometer.jpg
│     ├── fet-switch.jpg
│     ├── control-panel-1.jpg
│     ├── control-panel-2.jpg
│     └── lab-facility.jpg
│
└── docs/
      ├── manuals/           ← Product operations manuals (PDF)
      │     ├── MIPSoperationsManualR1_11.pdf
      │     ├── MIPS_User_Manual_v4_1.pdf
      │     ├── RFgeneratorR2_0.pdf
      │     ├── RFmegaR3_1.pdf
      │     ├── MFT_R4_0.pdf
      │     ├── SLIMrev4_0.pdf
      │     ├── Electrometer4_0.pdf
      │     ├── FET_TW_switchR3_0.pdf
      │     ├── LDMrev1_0.pdf
      │     ├── MIPSquadOperationsR3_0.pdf
      │     └── FAIMS_3_0.pdf
      └── resources/         ← Business documents (PDF)
            ├── RateSheet03292026.pdf
            ├── Warranty_Statement.pdf
            └── ResourcesCapabilities.pdf
```

---

## Updating the Site

Content changes are managed via AI-assisted chat. After receiving an updated `index.html`:

1. Go to this repository on github.com
2. Click `index.html` → click the pencil (edit) icon
3. Select all → paste new content
4. Click **Commit changes**
5. Site updates live within ~60 seconds

### Adding a new photo
1. Go to the `images/` folder in this repository
2. Click **Add file → Upload files**
3. Drag in the photo with the correct filename
4. Commit — the HTML already references it by filename

### Adding or updating a manual PDF
1. Go to `docs/manuals/`
2. Upload the PDF (same filename = automatic replacement, no HTML change needed)
3. New document? Add a download row to the HTML via the update process above

---

## GitHub Pages Setup

This site is hosted via **GitHub Pages** at:
`https://GordonAnderson.github.io/gaacustom/`

Custom domain configured: `www.GAAcustom.com`

To enable Pages on a new repository:
- Settings → Pages → Source: main branch / root → Save

---

## MIPS Software

The MIPS host application and all firmware/hardware source files are maintained in separate repositories:
- [github.com/GordonAnderson](https://github.com/GordonAnderson)

---

## Contact

**GAA Custom Electronics, LLC**  
101904 Wiser Parkway, Suite 105  
Kennewick, WA 99320  

📞 509.628.6851  
✉️ gaa@gaa-ce.com  
🌐 www.GAAcustom.com

---

*Website developed and maintained with AI assistance via Claude (Anthropic).*
