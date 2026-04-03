<div align="center">

# 🚲 KreherNavi
### Satellitengestützte Navigation für Lastenräder & Co.

[![PWA](https://img.shields.io/badge/PWA-Ready-green?style=flat-square)](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Deployed-blue?style=flat-square)]()
[![No Backend](https://img.shields.io/badge/No%20Backend-100%25%20Client-brightgreen?style=flat-square)]()

**Dein Lastenrad-Navi: Ohne App Store, ohne Backend, ohne Datensammlung.**

</div>

---

> [!IMPORTANT]
> **Haftungsausschluss:** Der Namensgeber **ReneKreher** hat nichts mit der Entwicklung der App zu tun! Dies ist ein **Fanmade Projekt** von [nicetoTECHyou (Twitch)](https://twitch.tv/nicetoTECHyou), um Renes Projekte & Reisen zu unterstützen und die Suche nach Charging- & Camping-Spots zu erleichtern.

---

## 📱 Installation (PWA)
KreherNavi ist eine **Progressive Web App**. Du kannst sie ohne App Store direkt auf deinem Home-Bildschirm installieren:

| Plattform | Anleitung |
| :--- | :--- |
| 🤖 **Android** | Chrome öffnen → ⋮ Menü → **"App installieren"** |
| 🍎 **iOS** | Safari öffnen → ☐↑ Teilen → **"Zum Home-Bildschirm"** |
| 🖥️ **Desktop** | Chrome/Edge → ⊕ **Installations-Icon** in der Adressleiste |

---

## ✨ Features

### 🗺️ Navigation & Karten
* **Hochauflösende Satellitenbilder:** Nutzung von ESRI World Imagery.
* **Intelligentes Routing:** Fahrradoptimierte Strecken via BRouter-API.
* **Interaktive Planung:** Wegpunkte per Klick & Drag setzen; bis zu 3 Alternativrouten.
* **Live-Modus:** Turn-by-Turn-Navigation mit animierter Fahrzeuganzeige & Kompass.
* **Simulationsmodus:** Routen vorab mit 1x bis 50x Geschwindigkeit virtuell abfahren.

### 🚲 Fahrzeugprofile
Wähle dein passendes Profil für präzise Ankunftszeiten (10–60 km/h einstellbar):
* **Cargo-Linie:** Cargo Bike (Standard), E-Cargo & Pedelec.
* **Sport:** MTB (Gelände) & Race Bike (Straße).
* **Easter Egg:** **DeLorean** mit speziellem "Flux-Kompensator" Effekt.

### 🔍 POIs & Suche
* **Adresssuche:** Schnellsuche via Nominatim / OpenStreetMap.
* **8 POI-Kategorien:** Burgen, Museen, Kirchen, Naturdenkmäler, Gastronomie, Unterkünfte, Verkehr & Industriekultur.

### 🌍 System & UI
* **Offline-Ready:** Dank Service Worker & Offline-Cache.
* **Anpassbar:** Dark Mode, Vollbildmodus, Drohnenansicht (3D) & Mehrsprachigkeit (DE/EN).
* **Export-Profi:** Unterstützt GPX, KML, TCX, CSV & Google Maps Direktlinks.

---

## 🛠️ Technische Details

| Komponente | Technologie |
| :--- | :--- |
| **Karte** | [MapLibre GL JS](https://maplibre.org/) v4.7 |
| **Routing** | [BRouter](https://brouter.de/) API |
| **Geocoding** | Nominatim (OSM) via JSONP |
| **POIs** | [Overpass API](https://overpass-api.de/) |
| **Styling** | Tailwind CSS + Custom CSS |
| **Architektur** | 100% Client-Side (Single-File HTML) |

### 📂 Dateistruktur
```text
├── navigation_v3.html      # Hauptdatei (Code & Assets)
├── manifest.json           # PWA-Manifest
├── sw.js                   # Service Worker (Cache)
├── icon-192.png            # App-Icon (Klein)
└── icon-512-final.png      # App-Icon (Groß)
````

-----

## 🚀 Letztes Update: Vehicle Marker Overhaul

### ✅ Neue Top-Down Marker

Alle Fahrzeugmarker wurden von einfachen SVGs auf hochwertige Base64-PNGs umgestellt:

| Vehicle | Beschreibung | Design-Stil |
| :--- | :--- | :--- |
| **Mountain Bike** | Breite Stollenreifen, Federgabel | 🟠 Orange / Dark Gray |
| **Racing Bike** | Aero-Reifen, Drop-Bars | 🔴 Red / Carbon Black |
| **DeLorean** | Edelstahl-Body, Flügeltüren | 🔘 Silver / Blue Glass |
| **DeLorean 🔥** | **Flux Mode:** Blitze & Flammenspuren | ⚡ Neon Blue / Orange |

> [\!TIP]
> **Easter Egg:** NEEDS FIX - Bei einer Geschwindigkeit von **\>88 km/h** wechselt der DeLorean-Marker automatisch in den flammenden Flux-Modus inkl. Cyan-Glow UI\! 

> [\!WARNING]
> **Known Issues:** Aktuell ist nur `FRANKY` ein finales Top-Down Modell. Die anderen Marker werden in der nächsten Version noch verfeinert.

-----


## 🔗 Social Media & Lizenz

**Datenquellen:**

  * 🗺️ Karten: [OpenStreetMap](https://www.openstreetmap.org/) (ODbL)
  * 🛰️ Satellit: [ESRI World Imagery](https://www.esri.com/)

## 📺 Support & Community

Begleite **Rene Kreher** live bei seinen Projekten und Reisen:

[![Twitch Status](https://img.shields.io/badge/Live_auf-Twitch-purple?style=for-the-badge&logo=twitch&logoColor=white)](https://www.twitch.tv/renekreher)



<!-- end list -->

```
```
