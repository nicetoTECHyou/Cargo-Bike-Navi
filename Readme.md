<div align="center">

# 🚲 CargoNavi
### Satellitengestützte Navigation für Lastenräder & Co.

[![PWA](https://img.shields.io/badge/PWA-Ready-green?style=flat-square)](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Deployed-blue?style=flat-square)]()
[![No Backend](https://img.shields.io/badge/No%20Backend-100%25%20Client-brightgreen?style=flat-square)]()
[![Voice Nav](https://img.shields.io/badge/Voice-Navigation-8b5cf6?style=flat-square)]()
[![GPS](https://img.shields.io/badge/GPS-Realtime-3b82f6?style=flat-square)]()

**Dein Lastenrad-Navi: Ohne App Store, ohne Backend, ohne Datensammlung und vor allem ohne Kosten.**

<br>

[![Open CargoNavi](https://img.shields.io/badge/🚲_CargoNavi_öffnen-Navi_Starten-2ea44f?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0xMiAyQzYuNDggMiAyIDYuNDggMiAxMnM0LjQ4IDEwIDEwIDEwIDEwLTQuNDggMTAtMTBTMTcuNTIgMiAxMiAyem0tMiAxNWwtNS01IDEuNDEtMS40MUwxMCAxNC4xN2w3LjU5LTcuNTlMMTkgOGwtOSA5eiIvPjwvc3ZnPg==)](https://nicetotechyou.github.io/Cargo-Bike-Navi/navigation_v3.html)

</div>

---

## 📱 Installation (PWA)
CargoNavi ist eine **Progressive Web App**. Du kannst sie ohne App Store direkt auf deinem Home-Bildschirm installieren:

| Plattform | Anleitung |
| :--- | :--- |
| 🤖 **Android** | Chrome öffnen → ⋮ Menü → **"App installieren"** |
| 🍎 **iOS** | Safari öffnen → ☐↑ Teilen → **"Zum Home-Bildschirm"** |
| 🖥️ **Desktop** | Chrome/Edge → ⊕ **Installations-Icon** in der Adressleiste |

---

## ✨ Features

### 🗺️ Navigation & Karten
* **Hochauflösende Satellitenbilder:** Nutzung von ESRI World Imagery.
* **Echte GPS-Navigation:** Start Navigation nutzt das echte GPS-Signal deines Geräts — Fahrzeugmarker folgt deiner Position in Echtzeit.
* **Demo-Modus:** Separater Button zum virtuellen Abfahren der Route mit animiertem Fahrzeug.
* **Intelligentes Routing:** Fahrradoptimierte Strecken via BRouter-API.
* **Interaktive Planung:** Wegpunkte per Klick & Drag setzen; bis zu 3 Alternativrouten.
* **Echte Geschwindigkeit:** GPS-Modus zeigt deine reale Geschwindigkeit in km/h an.
* **Auto-Arrival:** Erkennt automatisch wenn du within 30m des Ziels ankommst.
* **Höhenprofil:** Anstieg & Abstieg der Route automatisch berechnet und angezeigt.
* **Fahrzeugabmessungen:** Breite & Höhe eingeben — Route vermeidet enge Wege & niedrige Brücken.
* **Autobahnen meiden:** Schalter zum Vermeiden von highways/motorways.

### 🗣️ Sprachnavigation & Lautstärke
* **Turn-by-Turn Ansagen:** Kündigt Abbiegungen automatisch per Stimme an — kein Hinsehen nötig.
* **GPS-basierte Ansagen:** Sprachnavigation arbeitet mit dem echten GPS-Signal in Echtzeit.
* **Distanz-Trigger:** Ansagen bei 500m, 300m, 200m, 100m, 50m vor dem Abbiegepunkt.
* **Sofort-Ansagen:** *"Jetzt rechts abbiegen"* wenn du direkt am Abbiegepunkt bist.
* **Zielankunft:** Automatische Ansage *"Sie haben Ihr Ziel erreicht"*.
* **Mute-Button:** Stiller Schalter (🔇) in der Sidebar und auf der Karte während der Navigation.
* **Lautstärke-Regler:** Slider (0–100%) zum Einstellen der Sprachlautstärke.
* **Sprechtempo:** Wählbare Geschwindigkeit: 0.8x, 1x, 1.2x, 1.5x.
* **Mehrsprachig:** Sprachausgabe wechselt automatisch zwischen Deutsch und Englisch.
* **Kein Backend:** Nutzt die Web Speech API des Browsers — funktioniert komplett offline.
* **Ein-/Ausschaltbar:** Schalter in der Sidebar zum Deaktivieren der Sprachausgabe.

### ⚠️ Routen-Überwachung (NEU)
* **Off-Route Erkennung:** Warnt dich wenn du mehr als 50m von der geplanten Route abkommst.
* **Falsche-Fahrtrichtung Erkennung:** Erkennt wenn du in die falsche Richtung fährst (>135° Abweichung).
* **Smart gedrosselt:** Warnungen maximal alle 10–15 Sekunden — kein Spam.
* **GPS-basiert:** Nutzt die Live-GPS-Position für präzise Abweichungserkennung.

### 🚲 Fahrzeugprofile
Wähle dein passendes Profil für präzise Ankunftszeiten (1–200 km/h einstellbar):
* **Cargo-Linie:** FRANKY — Das Lastenrad mit eigenem Top-Down-Marker.
* **Sport:** Mountain Bike (Gelände) & Racing Bike (Straße) — jeweils mit eigenen Top-Down-Markern.
* **Easter Egg:** **DeLorean** mit speziellem "Flux-Kompensator" Effekt bei ≥88 km/h.

### 🔍 POIs & Suche
* **Adresssuche:** Schnellsuche via Nominatim / OpenStreetMap.
* **⚡ EV Ladestationen:** Echtzeit-Suche mit Betreiber, Steckertypen & Kosteninfo.
* **⛺ Campingplätze:** Camping- und Stellplätze mit Details zu Zelten, Wohnwagen & WiFi.
* **📸 Sehenswürdigkeiten:** Burgen, Schlösser, Museen, Kirchen, Denkmäler, Ruinen, Aussichtspunkte & mehr.
* **POI-Liste:** Sortierte Übersicht der nächsten POIs mit Entfernung und Detail-Infos.

### 🌍 System & UI
* **Offline-Ready:** Dank Service Worker & Offline-Cache (inklusive Fahrzeugbilder).
* **Dark Mode:** Helles und dunkles Theme per Klick umschaltbar.
* **Kartenstile:** Satellit, Topographisch, Straßenkarte & Dunkle Karte.
* **Ansichten:** Folgemodus (hinter dem Fahrzeug) & Drohnenansicht (3D rotierend).
* **Vollbildmodus:** Komplett auf die Karte fokussieren — UI ein-/ausblenden.
* **Mehrsprachig:** Deutsch & Englisch per Klick umschaltbar.
* **GPS Live-Tracking:** Eigene Position mit Genauigkeitskreis & Kompass-Indikator.
* **Responsive Design:** Optimiert für Smartphone, Tablet & Desktop.
* **Export-Profi:** Unterstützt GPX, KML, TCX, CSV & Google Maps Direktlinks.
* **Tastenkürzel:** Strg+N (Navigation), Strg+D (Dark Mode), Strg+F (Vollbild), Esc (Schließen).

---

## 🛠️ Technische Details

| Komponente | Technologie |
| :--- | :--- |
| **Karte** | [MapLibre GL JS](https://maplibre.org/) v4.7 |
| **Routing** | [BRouter](https://brouter.de/) API |
| **Geocoding** | Nominatim (OSM) via JSONP |
| **POIs** | [Overpass API](https://overpass-api.de/) |
| **Sprachausgabe** | Web Speech API (`speechSynthesis`) |
| **Styling** | Tailwind CSS + Custom CSS |
| **Architektur** | 100% Client-Side (Single-File HTML) |

### 📂 Dateistruktur
```text
├── navigation_v3.html      # Hauptdatei (Code & Assets)
├── manifest.json           # PWA-Manifest
├── sw.js                   # Service Worker (Offline-Cache)
├── icon-192.png            # App-Icon (192×192)
├── icon-512-final.png      # App-Icon (512×512)
├── FRANKY.png              # Fahrzeugmarker — Cargo Bike
├── mtb_topdown.png         # Fahrzeugmarker — Mountain Bike
├── racingbike_topdown.png  # Fahrzeugmarker — Racing Bike
└── delorean_topdown.png    # Fahrzeugmarker — DeLorean
```

---

## 🚀 Changelog

### [v3.3] — Echte GPS-Navigation & Lautstärke-Steuerung
**Datum:** 2026-04-04

**Neu:**
- 📍 **Echte GPS-Navigation:** "Start Navigation" nutzt das echte GPS-Signal — Fahrzeugmarker, Geschwindigkeit und Richtung folgen deiner Position in Echtzeit
- 🎮 **Demo-Modus:** Separater Button zum virtuellen Abfahren der Route mit Animation
- 🔇 **Mute-Button:** Stiller Schalter in der Sidebar + Schnell-Mute auf der Karte während der Navigation
- 🔊 **Lautstärke-Regler:** Volume-Slider (0–100%) in der Sidebar
- ⏩ **Sprechtempo:** Wählbare Geschwindigkeit: 0.8x, 1x, 1.2x, 1.5x
- 🏁 **Auto-Arrival:** Erkennt automatisch wenn du innerhalb 30m des Ziels ankommst
- 💨 **Echte Geschwindigkeit:** Zeht die reale GPS-Geschwindigkeit in km/h an

**Verbessert:**
- Off-Route Erkennung nutzt jetzt Point-to-Line-Segment Distanz (genauer als Punkt-zu-Punkt)
- Sprachnavigation arbeitet jetzt mit dem echten GPS-Signal (nicht nur Simulation)
- Distanz-Trigger für Ansagen optimiert (1,5s statt 3s Mindestintervall)
- Dead '20m' Bracket aus der Ansagen-Logik entfernt

### [v3.2] — Sprachnavigation & Routen-Überwachung
**Datum:** 2026-04-04

**Neu:**
- 🗣️ Vollständiges Voice-Navigationssystem mit Web Speech API
- Distanzbasierte Turn-by-Turn-Ansagen (500m → 20m → "Jetzt")
- Off-Route Warnung bei >50m Abweichung von der geplanten Route
- Falsche-Fahrtrichtung Erkennung (>135° Gegenrichtung)
- 22 neue i18n-Strings für Sprachausgabe (DE/EN)
- Sprachnavigation Toggle-Schalter in der Sidebar

**Geändert:**
- Intelligente Look-Ahead-Kurvensuche (scannt bis zu 200 Punkte voraus)
- GPS-Position verknüpft mit Routen-Abweichungs-Check
- Fahrzeugbilder zum Service Worker Precache hinzugefügt

### [v3.1] — Fahrzeug-Marker Overhaul
**Datum:** 2026-04-04

**Geändert:**
- Alle Fahrzeugmarker auf Top-Down-Bilddateien umgestellt (nose-north)
- Base64-Daten entfernt (~340 KB Einsparung, 65% kleinere HTML-Datei)
- Konsistente Darstellung zwischen Fahrzeugkarten und Kartenmarkern
- DeLorean Easter Egg auf CSS-Glow-Effekte umgestellt (kein Bild-Swap mehr)

---

## 🤖 Gebaut mit Z.ai — KI-Assistent

Dieses Projekt wurde mit Unterstützung von **Z.ai**, einem leistungsstarken KI-Assistenten von Zhipu AI entwickelt. Von der Architektur über die GPS-Navigation bis zur Sprachsteuerung — Z.ai war dabei als kreativer Partner an meiner Seite und hat maßgeblich dazu beigetragen, CargoNavi zu dem zu machen, was es heute ist.

[![Powered by Z.ai](https://img.shields.io/badge/Powered_by-Z.ai-0ea5e9?style=for-the-badge)](https://chat.z.ai)

---

## 🔗 Social Media & Lizenz

**Datenquellen:**

  * 🗺️ Karten: [OpenStreetMap](https://www.openstreetmap.org/) (ODbL)
  * 🛰️ Satellit: [ESRI World Imagery](https://www.esri.com/)

## 📺 Support & Community

Begleite **Rene Kreher** live bei seinen Projekten und Reisen - Er war die Inspiration dieses Navi zu Programmieren , da es nicht wirklich gute Kostenlose Navis gibt die so viel umfang bieten eine route zu planen.

[![Twitch Status](https://img.shields.io/badge/Live_auf-Twitch-purple?style=for-the-badge&logo=twitch&logoColor=white)](https://www.twitch.tv/renekreher)

> [!IMPORTANT]
> **Haftungsausschluss:** **ReneKreher** hat nichts mit der Entwicklung der App zu tun! Dies ist ein **Fanmade Projekt** von [nicetoTECHyou (Twitch)](https://twitch.tv/nicetoTECHyou), um Rene´s Projekte & Reisen zu unterstützen und die Suche nach Strecken , Sehenswürdigkeiten , Charging- & Camping-Spots zu erleichtern.

---
