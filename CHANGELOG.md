# Changelog — CargoNavi Navigation System

## [Voice Navigation + PWA Icons] - 2026-04-04

### Added
- **Voice Navigation System** — Full turn-by-turn voice guidance using Web Speech API (no external services needed):
  - Announces upcoming turns at distance thresholds: 500m, 300m, 200m, 100m, 50m, 20m
  - "Turn now" announcements when within 20m of a turn
  - Arrival announcement when reaching destination
  - Automatic language detection (German/English) based on app language setting
  - Voice toggle switch in sidebar (Options section) — enabled by default
  - Smart look-ahead scanning: finds the NEXT turn ahead on the route, not just the current segment angle
- **Off-Route Detection** — Warns when GPS position deviates more than 50m from the planned route:
  - "You have left the route" voice warning (throttled: max once per 15 seconds)
- **Wrong-Way Detection** — Detects when heading is opposite to route direction (>135° difference):
  - "Wrong way! Please turn around" voice warning (throttled: max once per 10 seconds)
  - Only triggers when within 30m of route (to avoid false positives from GPS drift)
- **22 new i18n strings** for voice navigation in both German and English
- **512x512 icon** added to HTML `<link>` tags for PWA manifest
- **Vehicle images** added to Service Worker precache list for full offline support

### Changed
- **`updateNavInstructions()`** rewritten with smarter turn detection:
  - Scans up to 200 points ahead to find the NEXT turn (skips minor bends <20°)
  - Calculates accurate distance to the upcoming turn using haversine formula
  - Shows "now" instruction when within 30m of a turn point
  - Integrates with VoiceNav engine for spoken announcements
- **`startNavigation()`** now initializes and resets voice engine
- **`stopNavigation()`** now cancels any pending voice announcements
- **`onGpsPositionUpdate()`** now calls route deviation check during navigation
- **`sw.js`** — added vehicle images (FRANKY.png, mtb_topdown.png, racingbike_topdown.png, delorean_topdown.png) to precache list

### Technical Notes
- Voice uses Web Speech API (`window.speechSynthesis`) — works in all modern browsers without API keys
- Best voice quality on Chrome (Android/desktop), Safari (iOS), Edge
- Firefox support varies — some platforms may have limited voices
- Voice preloading handled via `speechSynthesis.onvoiceschanged` event
- Minimum 3-second throttle between announcements to prevent speech overlap
- Off-route threshold: 50m | Wrong-way heading threshold: >135° difference
- `manifest.json` restored with `purpose: "any maskable"` for proper PWA icon handling

### File Structure
```
├── navigation_v3.html
├── manifest.json
├── sw.js
├── icon-192.png
├── icon-512-final.png
├── FRANKY.png
├── mtb_topdown.png
├── racingbike_topdown.png
└── delorean_topdown.png
```

---

## [Vehicle Image System] - 2026-04-04

### Changed
- **Vehicle cards** now use file-path referenced images instead of inline data:
  - `FRANKY.png` — Cargo Bike (nose pointing north)
  - `mtb_topdown.png` — Mountain Bike (nose pointing north)
  - `racingbike_topdown.png` — Racing Bike (nose pointing north)
  - `delorean_topdown.png` — DeLorean (nose pointing north)
- **Vehicle map markers** (`getVehicleSVG()`) now use the same file-path images for consistent appearance between cards and map
- All vehicle images are oriented **nose-north** (top-down view) as the default orientation
- DeLorean Back-to-the-Future easter egg (>= 88 km/h speed effect) now uses CSS glow effects only, without swapping marker images

### Removed
- `DELOREAN_FLAME_IMG` — Removed inline base64 PNG data (~212 KB)
- `DELOREAN_NORMAL_IMG` — Removed inline base64 PNG data (~127 KB)
- **Total reduction**: ~340 KB of inline base64 data removed from `navigation_v3.html`
- Image swap logic in speed simulation code that referenced the removed base64 constants

### Notes
- File size reduced from ~515 KB to ~183 KB (65% smaller)
- All vehicle images must be co-located with `navigation_v3.html` in the same directory
- The "van" vehicle still uses an inline SVG marker (no external image uploaded)
