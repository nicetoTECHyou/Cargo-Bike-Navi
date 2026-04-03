# 🚲 KreherNavi — Cargo Bike Navigation System

<div align="center">

**Satellitengestützte Fahrrad-Navigation für Lastenräder & Co.**

Der Namensgeber ReneKreher hat nichts mit der Entwicklung der App zu tun !! Fanmade Projekt von nicetoTECHyou(Twitch) um Rene seine Projekte & Reisen zu unterstützen und die suche nach Charging & Camping Spots zu erleichtern. 

[![PWA](https://img.shields.io/badge/PWA-Ready-green?style=flat-square)](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Deployed-blue?style=flat-square)]()
[![No Backend](https://img.shields.io/badge/No%20Backend-100%25%20Client-brightgreen?style=flat-square)]()

</div>

---

## 📱 Als App installieren (PWA)

KreherNavi ist eine **Progressive Web App** — du kannst sie direkt auf deinem Gerät installieren:

| Plattform | So geht's |
|---|---|
| 🤖 **Android** | Chrome öffnen → ⋮ Menü → **"App installieren"** |
| 🍎 **iOS** | Safari öffnen → ☐↑ Teilen → **"Zum Home-Bildschirm"** |
| 🖥️ **Desktop** | Chrome/Edge → ⊕ Installations-Icon in der Adressleiste |

Die App funktioniert dann wie eine native App — ohne Play Store oder App Store!

---

## ✨ Features

### 🗺️ Karte & Navigation
- **Satelliten-Karte** (ESRI World Imagery, hochauflösende Luftbilder)
- **Routenberechnung** per BRouter-API (fahrradoptimierte Routen)
- **Turn-by-Turn-Navigation** mit animierter Fahrzeuganzeige
- **Simulationsmodus** — Route animiert abfahren (wählbare Geschwindigkeit 1x–50x)
- **Wegpunkte** auf der Karte setzen per Klick & Drag
- **Alternative Routen** — bis zu 3 Routenvorschläge

### 🚲 Fahrzeugprofile
- **Cargo Bike** (Lastenrad) — Standardprofil
- **MTB** (Mountainbike) — für Geländerouten
- **Race Bike** (Rennrad) — für schnelle Straßenrouten
- **Pedelec** — E-Bike mit Motorunterstützung
- **E-Cargo** (Lasten-E-Bike)
- **DeLorean** — mit Flammenspur-Effekt (Fun-Modus)
- Individuelle **Geschwindigkeit** einstellbar (10–60 km/h)
- **Routing-Profile**: Fast / MTB / Car / Walk

### 🔍 Suche & Geocoding
- Orts- und Adresssuche (Nominatim / OpenStreetMap)
- **Standortermittlung** per GPS (Geolocation API)
- Start-/Ziel-Eingabe oder per Map-Klick setzen

### 📍 POI-Schichten (Sehenswürdigkeiten)
8 Kategorien touristischer Punkte von Interesse:
- 🏰 Burgen & Schlösser
- 🏛️ Museen & Gallerien
- ⛪ Kirchen & historische Gebäude
- 🏞️ Naturdenkmäler & Parks
- 🍽️ Gastronomie
- 🏨 Unterkünfte
- 🚂 Verkehr & Transport
- 🏗️ Industriekultur

### 🌍 Kartenfunktionen
- **Kartenauswahl**: Satellit / OpenStreetMap / Topografisch
- **Dunkelmodus** (Dark Mode)
- **Vollbildmodus**
- **Drohnenansicht** (3D-Perspektive)
- **Zoom zum Standort**
- Kompass-Richtung

### 📤 Export & Teilen
- **GPX-Export** (GPX Track + Route)
- **KML-Export** (Google Earth)
- **TCX-Export** (Garmin/Wahoo)
- **CSV-Export** (Wegpunkte als Tabelle)
- **Google Maps Direktlink** zur berechneten Route

### 🌐 Mehrsprachigkeit
- 🇩🇪 Deutsch
- 🇬🇧 English
- Sprachwechsel per Flaggen-Button

### 📱 Mobile & PWA
- Vollständig **responsive** (Handy, Tablet, Desktop)
- **Touch-optimiertes** Seitenmenü
- **Offline-Cache** via Service Worker
- **Installierbar als App** auf Android, iOS & Desktop
- **Standalone-Modus** — läuft ohne Browser-UI

---

## 🚀 Deployment (GitHub Pages)

### Dateistruktur

```
dein-repo/
├── navigation_v3.html      ← Hauptdatei (alles in einer Datei)
├── manifest.json           ← PWA-Manifest
├── sw.js                   ← Service Worker (Offline-Cache)
├── icon-192.png            ← App-Icon (192×192)
├── icon-512-final.png      ← App-Icon (512×512)
└── README.md               ← Diese Datei
```

### Anleitung

1. **Repository erstellen** auf [github.com](https://github.com)
2. Alle Dateien in das Repository hochladen
3. **Settings → Pages → Source** auf `main` Branch setzen
4. Nach ~1 Minute ist die Seite unter `https://username.github.io/repo-name/navigation_v3.html` erreichbar
5. Repo muss **öffentlich** sein (für kostenlose GitHub Pages)

---

## 🛠️ Technische Details

| Aspekt | Technologie |
|---|---|
| Karte | [MapLibre GL JS](https://maplibre.org/) v4.7 |
| Satellitenbilder | ESRI World Imagery |
| Routing | [BRouter](https://brouter.de/) API |
| Geocoding | Nominatim (OpenStreetMap) via JSONP |
| POI-Daten | [Overpass API](https://overpass-api.de/) |
| Icons | [Font Awesome](https://fontawesome.com/) 6.5 |
| Styling | Tailwind CSS + Custom CSS |
| Architektur | Single-File HTML (kein Build-Step) |
| Backend | ❌ Keins — 100% Client-Side |
| CORS | Alle APIs CORS-freundlich |

### APIs (alles kostenlos, kein API-Key nötig)

- **BRouter**: Fahrrad-Routing mit Custom-Profile
- **Nominatim**: Geocoding / Adresssuche
- **Overpass**: POI-Abfragen (OpenStreetMap)
- **ESRI**: Satelliten- & Topografiekarten-Tiles

# Social Media

Folgen Sie Herrn Kreher auf Twitch:

[![Twitch Status](https://img.shields.io/badge/Twitch-renekreher-purple?style=for-the-badge&logo=twitch)](https://www.twitch.tv/renekreher)

---
[Jetzt auf Twitch ansehen >>](https://www.twitch.tv/renekreher)

## 📋 Lizenz

Dieses Projekt nutzt die folgenden Dienste und Datenquellen:

- 🗺️ Kartendaten: [OpenStreetMap](https://www.openstreetmap.org/) (ODbL)
- 🛰️ Satellitenbilder: [ESRI](https://www.esri.com/) (Lizenz siehe [ESRI Terms](https://www.esri.com/en-us/legal/terms/terms-of-use))

---
KNOWN BUGS : Only FRANKY is a Top Down Model .. Fix in next version 

Fixed: XSS via unsanierte OSM-Daten in Popups
Fixed: XSS in buildAddToRouteButtons()
Fixed: javascript: URL Injection via props.website
Fixed: Abbiege-Erkennung — unreachable code
Fixed: simSpeed Initialwert falsch (1 statt 30)
Fixed: Fehlender i18n-Key 'end_set'
Fixed: Alt-Routen-Panel nicht wieder sichtbar nach Nav-Stopp
Fixed: GPS easeTo queued auf schnellen Updates
Fixed: view-controls right:230px auf Mobile
---

<div align="center">

**KreherNavi** — Dein Lastenrad-Navi, ohne App Store, ohne Backend, ohne Datensammlung.

</div>
