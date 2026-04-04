# Changelog — CargoNavi Navigation System

## [v3.4] — Auto-Center & Auto GPS Tracking - 2026-04-05

### Added
- **Auto-Center on Load** — Map automatically centers on user location when the app loads:
  - Uses `getCurrentPosition()` with high accuracy and 8s timeout
  - Smooth flyTo animation (1.5s) to user position at zoom level 14
  - Silent fallback to default center (Berlin) if permission denied
- **Auto GPS-Tracking** — GPS live tracking starts automatically on app load:
  - No button click needed — tracking begins immediately after map load
  - Shows GPS marker, accuracy circle, and heading indicator
  - GPS button remains functional for toggling tracking on/off
  - Guarded: won't activate if GPS navigation is already running

### Technical Notes
- Both features trigger inside `map.on('load')` callback, after POI sources are initialized
- `getCurrentPosition()` handles error silently (empty callback) to avoid toast spam on first load
- `startGpsTracking()` already has built-in guard against duplicate activation

---

## [v3.3] — Real GPS Navigation & Volume Controls - 2026-04-04

### Added
- **Real GPS Navigation Mode** — "Start Navigation" now uses the device's real GPS signal:
  - Vehicle marker follows your actual GPS position in real-time
  - Real speed displayed from GPS (km/h), or calculated from consecutive position fixes
  - Heading from GPS compass or derived from position deltas
  - Vehicle marker hidden until first GPS fix, then map flies to your position
  - Auto-arrival detection when within 30m of destination
  - Off-route and wrong-way voice warnings during GPS navigation
- **Demo Mode** — Separate button for animated route simulation:
  - Isolated from GPS navigation — both modes cannot run simultaneously
  - Demo button shows "Stop Demo" with orange styling when active
  - Start Navigation button shows "Stop Navigation" with red styling when active
  - Inactive button is greyed out during either mode
- **Volume Controls in Sidebar** — Always visible below Voice Navigation toggle:
  - **Mute button** — Tap to mute/unmute, turns red when muted, synced with map quick-mute
  - **Volume slider** — 0–100% with large touch-friendly 22px thumb
  - **Voice speed** — 0.8x, 1x, 1.2x, 1.5x speech rate buttons
  - Dark mode support for all controls
- **Quick Mute Button on Map** — Visible during navigation (bottom-right):
  - Simple tap toggles mute — synced with sidebar mute button
- **8 new i18n strings** for GPS navigation and volume controls (DE/EN)
- **`state.navMode`** property to track active mode ('gps' or 'demo')

### Changed
- **`startNavigation()`** rewritten — now starts real GPS navigation via `watchPosition()`:
  - Creates vehicle marker at last known GPS position or route start
  - Uses dedicated `onNavGpsPositionUpdate()` handler for navigation updates
  - High accuracy GPS (1000ms max age, 15s timeout)
- **`startDemoNavigation()`** extracted — contains the old simulation/animation code
- **`stopNavigation()`** updated to handle both modes:
  - Clears GPS watch for GPS mode, cancels animation frame for demo mode
  - Resets both Start Navigation and Demo Mode buttons
  - Resets DeLorean speed display effects
- **`onNavGpsPositionUpdate()`** — new dedicated GPS handler for navigation mode:
  - Moves vehicle marker to GPS position
  - Calculates heading from GPS or consecutive position fixes
  - Shows real speed from GPS hardware
  - Triggers voice announcements based on nearest route point
  - Detects arrival within 30m of destination
  - Updates accuracy circle
  - Camera follow with bearing and pitch
- **`onGpsPositionUpdate()`** (standalone GPS tracking) — added guard to skip during GPS navigation
- **`startGpsTracking()`** — added guard to prevent starting when GPS navigation is active
- **`distToRoute()`** improved — uses point-to-line-segment projection instead of point-to-point distance:
  - Much more accurate for determining how far the user is from the route
  - Now returns `nearestIdx` for voice instruction lookup
- **Voice Navigation improvements:**
  - `VoiceNav.minInterval` reduced from 3000ms to 1500ms for more responsive announcements
  - `getBracket()` threshold changed from 20m to 15m for "now" announcements
  - Dead '20' bracket removed from `bracketOrder` array
  - `VoiceNav.speak()` now respects `volume` and `muted` properties
  - `utterance.rate` uses configurable `VoiceNav.rate` instead of hardcoded 1.0
- **`toggleMute()`** updated — syncs both sidebar and map mute buttons simultaneously

### Technical Notes
- GPS heading fallback: if device doesn't provide heading, it's calculated from consecutive GPS positions (max 5s delta)
- GPS speed fallback: if device doesn't provide speed, it's calculated from haversine distance between consecutive fixes
- Point-to-line-segment distance uses coordinate projection with clamped parameter [0,1]
- Both navigation modes share: vehicle marker, nav instructions, voice engine, speed display, follow/drone camera
- Volume controls use CSS `-webkit-appearance: none` for consistent cross-browser slider styling
- All controls have `touch-action: manipulation` to prevent double-tap zoom on mobile

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

## [v3.2] — Voice Navigation + PWA Icons - 2026-04-04

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
