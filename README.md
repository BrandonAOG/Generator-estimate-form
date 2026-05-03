# Generator Installation Estimate — README

```markdown
# ⚡ AOG Generator Installation Estimate Form

A professional, single-page web application for generating, saving, and
sharing generator installation estimates. Built for **Always On Generators**
field estimators.

---

## 🚀 Live Demo

> https://brandonaog.github.io/AOG-estimate/   ← update with your actual URL

---

## 📋 Features

### Core Functionality
- **Customer & Property Info** — Name, address (with autocomplete), HOA,
  phone, email, square footage, financing, survey status
- **Generator Section** — Size, placement, electrical run footage,
  wiring type, bore option, notes
- **Transfer Switch** — Panel count, switch type/placement, load shedding,
  coverage, ASE/Non-ASE, FPL/LCEC shutdown, grounding
- **Precast Pad** — Pad type, elevation, anchor method, notes
- **Fuel Tank** — Natural gas / propane, tank sizing, gas appliances
  checklist, underground / above-ground / attic run footage, bore
- **Install Details** — Difficulty rating, estimated days, new build flag,
  ready notes

### Smart UX
| Feature | Details |
|---|---|
| 🌙 Dark / Light Mode | Toggle with persistent localStorage preference |
| 🗓 Seasonal Themes | Auto-applies holiday decorations (Halloween, Christmas, etc.) |
| 📡 GPS Autofill | One-tap GPS → reverse-geocode address fill |
| 🔍 Address Autocomplete | Mapbox primary · Nominatim fallback · SW Florida priority |
| 💾 Auto-save Draft | Saves every 30 s + on every change (localStorage) |
| ✅ Form Validation | Real-time field validation with inline error messages |
| 📴 Offline Banner | Detects offline state and alerts the user |

### Export Options
| Button | Output |
|---|---|
| **PDF** | Triggers browser print dialog — Save as PDF |
| **IMAGE** | html2canvas → JPEG download (iOS opens in new tab) |
| **EMAIL** | Generates pre-filled `mailto:` with estimate summary |

---

## 🗂 File Structure

```
AOG-estimate/
├── index.html          ← Entire application (single file)
├── README.md           ← This file
└── assets/             ← (optional) local logo fallback
```

> The app is intentionally **one self-contained HTML file** so it can be
> opened directly from a phone's Files app with no server required.

---

## 🛠 Tech Stack

| Layer | Library / API |
|---|---|
| Fonts | Google Fonts — Orbitron · Share Tech Mono · Exo 2 |
| Image export | [html2canvas 1.4.1](https://html2canvas.hertzen.com/) (CDN) |
| Address search | [Mapbox Geocoding API](https://docs.mapbox.com/api/search/geocoding/) |
| Address fallback | [Nominatim / OpenStreetMap](https://nominatim.org/) |
| GPS | Browser `navigator.geolocation` |
| Storage | `window.localStorage` |
| Framework | **None** — Vanilla HTML/CSS/JS |

---

## ⚙️ Configuration

### Mapbox Token
Replace the token in `index.html` (line ~1050) with your own:

```js
var MAPBOX_TOKEN = 'pk.eyJ1IjoiWU9VUl9VU0VSTkFNRSIs...';
```

Get a free token at [mapbox.com](https://account.mapbox.com/).

### Company Logo
The logo is loaded from GitHub raw URL:

```html
<img src="https://raw.githubusercontent.com/BrandonAOG/AOG-Logo/main/logo.png">
```

Replace with your own hosted image or a `base64` data URI for offline use.

### SW Florida Geocoding Bias
Search results are biased toward Naples / Fort Myers / Cape Coral by default:

```js
var SW_FLORIDA_BBOX   = '-82.2,26.0,-81.2,27.0';
var SW_FLORIDA_CENTER = '-81.76,26.14';
```

Update the bounding box and center point to match your service area.

---

## 📱 Mobile Notes

| Platform | PDF | Image |
|---|---|---|
| Desktop | Print dialog → Save as PDF | Auto-downloads `.jpg` |
| Android | Print dialog → Save as PDF | Auto-downloads `.jpg` |
| iOS Safari | Share sheet → Save to Files | Opens in new tab → long-press to Save |

> **iOS tip:** After tapping PDF on Safari, pinch-zoom out on the page
> thumbnail before saving to fit the full form on one page.

---

## 🔒 Data & Privacy

- All form data is stored **only in the browser's localStorage** on the
  device — nothing is sent to any server.
- Clearing browser data / private browsing removes the draft.
- The EMAIL button opens the device's default mail client with a
  pre-filled body — no mail server is involved.

---

## 🗓 Seasonal Themes

The app automatically decorates itself based on the current date:

| Holiday | Dates |
|---|---|
| New Year | Jan 1–7 |
| Valentine's Day | Feb 1–28 |
| St. Patrick's Day | Mar 1–31 |
| Spring | Mar 20 – Jun 20 |
| Memorial Day | May 25–31 |
| Summer | Jun 21 – Sep 22 |
| Fourth of July | Jul 1–31 |
| Labor Day | Sep 1–7 |
| Halloween | Oct 1–31 |
| Thanksgiving | Nov 1–30 |
| Christmas | Dec 1–31 |

All seasonal decorations are automatically hidden during print/export.

---

## 🐛 Known Limitations

- Single page — no multi-page print support for very long notes.
- `html2canvas` may not render custom fonts on first capture; a brief
  delay before export resolves this in most cases.
- iOS Safari blocks direct file downloads; image export opens a new tab
  instead.

---

## 📄 License

Internal business tool — © Always On Generators. Not licensed for
redistribution.

---

## 👤 Author

**Brandon** — Always On Generators  
GitHub: [@BrandonAOG](https://github.com/BrandonAOG)
```

---

### Quick-copy badges you can paste at the top of the README

```markdown
![HTML](https://img.shields.io/badge/HTML-Single--File-orange?style=flat-square&logo=html5)
![Vanilla JS](https://img.shields.io/badge/JS-Vanilla-yellow?style=flat-square&logo=javascript)
![Mobile Ready](https://img.shields.io/badge/Mobile-Ready-blue?style=flat-square&logo=apple)
![No Framework](https://img.shields.io/badge/Framework-None-lightgrey?style=flat-square)
```
