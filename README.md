# 🔌 Always On Generators — Installation Estimate Form

![Version](https://img.shields.io/badge/version-1.0B-orange)
![License](https://img.shields.io/badge/license-MIT-green)
![HTML5](https://img.shields.io/badge/built%20with-HTML5-E34F26)
![Mobile Ready](https://img.shields.io/badge/mobile-optimized-blue)

A professional, single-file web application for capturing 
generator installation estimates in the field. Designed for 
tablet and mobile use by Always On Generators sales and 
estimating teams.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Usage Guide](#usage-guide)
- [Export Options](#export-options)
- [Form Sections](#form-sections)
- [Offline Support](#offline-support)
- [Mobile Optimization](#mobile-optimization)
- [Configuration](#configuration)
- [File Structure](#file-structure)
- [Browser Support](#browser-support)
- [License](#license)

---

## 🔍 Overview

The AOG Installation Estimate Form is a fully self-contained, 
single-file HTML application built for field estimators. It 
captures all necessary data points for a generator installation 
quote — customer info, property details, generator specs, 
transfer switch configuration, pad type, and fuel system — 
and exports the completed form as a print-ready PDF or JPEG image.

No backend required. No installation needed. Open in any 
modern browser and go.

---

## ✨ Features

### 📝 Form Capabilities
- **Customer Information** — Name, address with GPS autofill,
  phone, email, HOA/community
- **Property Details** — Square footage, gas type, financing,
  property survey, referral source
- **Generator Configuration** — Size, placement, electrical
  run footage, wiring type, bore requirements
- **Transfer Switch** — Panel count, switch type (ASE/Non-ASE),
  FPL/LCEC shutdown, load shedding, circuit counts, coverage
- **Precast Pad** — Type selection, elevation height, mounting
  method
- **Fuel Tank** — Natural gas vs propane, tank sizing, existing
  gas appliances checklist, run footage by path type
- **Install Metadata** — Difficulty rating, estimated days,
  new build flag, flood zone, parcel info

### 🖨️ Export Options
- **Print / PDF** — Device-aware print dialog with step-by-step
  instructions for iOS, Android, and desktop
- **Save as Image** — Full-form JPEG capture via html2canvas,
  scaled to 8.5" paper width, with iOS long-press lightbox and
  Android/desktop direct download

### 🔒 Data & Validation
- **Real-time field validation** with visual feedback
  (green = valid, red = invalid)
- **Auto-save draft** to localStorage every 30 seconds and on
  every change
- **Draft restore** on page reload — no data loss on refresh
- **Offline detection** with persistent warning banner

### 📍 Location Tools
- **Address autocomplete** powered by Mapbox Geocoding API
  (US addresses, live suggestions)
- **GPS autofill** via browser Geolocation + Nominatim reverse
  geocoding — populates street address and city/state/ZIP

---

## 🛠️ Tech Stack

| Layer        | Technology                            |
|--------------|---------------------------------------|
| Markup       | HTML5 (semantic, ARIA-labeled)        |
| Styling      | CSS3 (custom properties, flexbox,     |
|              | grid, clip-path, animations)          |
| Scripting    | Vanilla JavaScript (ES6+)             |
| Fonts        | Google Fonts — Orbitron, Share Tech   |
|              | Mono, Exo 2                           |
| Image Export | html2canvas v1.4.1 (CDN)             |
| Geocoding    | Mapbox Geocoding API v5               |
| Reverse Geo  | OpenStreetMap Nominatim               |
| Storage      | localStorage (draft persistence)      |
| Print        | Native browser print API              |

---

## 🚀 Getting Started

### Option 1 — Open Directly
```bash
# No build step needed — just open the file
open estimate-form.html
