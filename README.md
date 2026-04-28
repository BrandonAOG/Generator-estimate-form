# Always On Generators — Installation Estimate Form

A self-contained, single-file HTML estimate form for generator installation surveys. Built for field use on phones, tablets, and laptops. Works offline, saves automatically, and exports to PDF, image, or email.

## Features

- **Single HTML file** — no build step, no dependencies to install. Open in any browser.
- **Offline-ready** — auto-saves drafts to localStorage every 30 seconds and on every input change. A red banner warns when the device is offline.
- **Address autocomplete** — Mapbox Geocoding API for typing, plus a one-tap GPS button that reverse-geocodes via OpenStreetMap Nominatim.
- **Form validation** — real-time field-by-field validation with inline error messages and a summary modal that scrolls to the first invalid field.
- **Print to PDF** — works on iOS Safari, Android Chrome, and desktop. Platform-specific print instructions guide the user through saving as PDF.
- **Save as image** — captures the entire form as a JPEG via html2canvas, scaled to 8.5×11 paper proportions for clean printing or sharing.
- **Email export** — opens the user's default mail client with a pre-filled summary of the estimate.
- **Mobile-first design** — touch-friendly tap targets, no zoom-on-focus, safe-area insets for notched devices.

## Sections of the Form

1. **Customer Info** — name, address (with autocomplete + GPS), HOA, phone, email
2. **Property Info** — square footage, fuel type, financing, survey status, estimator details
3. **Flood / Parcel** — zone info and municipality
4. **Generator** — size, placement, electrical run footage, wiring type, bore option
5. **Transfer Switch** — panel count, switch type, coverage, load shedding
6. **Pad** — type (precast, poured, elevated, etc.), height, mounting style
7. **Fuel Tank** — natural gas vs propane, tank sizes, existing gas appliances, fuel line footage, install difficulty

## Tech Stack

- **Vanilla HTML / CSS / JavaScript** — no frameworks
- **html2canvas** (CDN) — for image export
- **Mapbox Geocoding API** — address autocomplete
- **OpenStreetMap Nominatim** — reverse geocoding for the GPS button
- **localStorage** — draft persistence
- **Google Fonts** — Orbitron, Share Tech Mono, Exo 2

## File Structure

This is a single-file project. Everything lives in `index.html`:
- Inline `<style>` block with all CSS
- Inline `<script>` blocks for print optimization, validation, and form actions
- All form markup

- git clone https://github.com/BrandonAOG/Generator-estimate-form.git

## Getting Started

1. Clone the repo:
2. Open `index.html` in a browser. That's it.

To deploy, host the file on any static web host (GitHub Pages, Netlify, Vercel, Cloudflare Pages). No server or build step required.

## API Keys

The Mapbox token is currently embedded in the file. If you fork this project, replace it with your own:

```javascript
var MAPBOX_TOKEN = 'your-token-here';
```

Mapbox tokens are scoped — restrict yours to your domain in the Mapbox dashboard.

## Print / PDF Notes

Printing across mobile browsers is inconsistent. This project uses platform-specific workarounds:

- **Desktop & Android** — JavaScript calculates a stretch scale and applies it via `transform: scale()` before printing, so the form fits one page regardless of content height.
- **iOS Safari** — uses a CSS-based approach (`zoom` + fixed page dimensions) and a forced layout reflow before `window.print()` to work around a known iOS bug where the first print attempt overflows to a second page.

Users on iOS may need to disable "Print Headers and Footers" in their print options to avoid Safari's URL/date footer on the printed page. This is a browser setting, not something the page can control.

## Browser Support

Tested on:
- iOS Safari 15+
- Chrome (desktop, Android)
- Firefox (desktop)
- Edge (desktop)

The form uses `:has()` for some styling (checked-state highlighting), which is supported in all current browsers but may degrade gracefully in older ones.

## Known Limitations

- The `zoom` CSS property used for iOS print scaling is non-standard but supported in all major browsers.
- Mapbox autocomplete requires network access; the GPS button requires location permission.
- Email export uses `mailto:` which depends on the user having a configured mail client.

## License

Proprietary. Internal use by Always On Generators.

## Contact

Always On Generators
