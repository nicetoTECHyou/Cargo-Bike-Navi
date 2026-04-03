# 🚀 KreherNavi — Cargo Bike Navigation System

KreherNavi ist ein leistungsstarkes, zu 100 % clientseitiges Navigationssystem, das speziell für Lastenräder und Spezialfahrzeuge entwickelt wurde. Es läuft direkt im Browser ohne Installation oder Backend.

---

## 🌟 Highlights
 Zero Installation Eine einzige HTML-Datei – einfach öffnen und loslegen.
 Privacy First 100 % Client-Side, keine Datenbank, keine Registrierung.
 Open Source Data Nutzt MapLibre, BRouter, OpenStreetMap und ESRI.
 Cargo-Optimiert Berücksichtigt Fahrzeugmaße (BreiteHöhe) bei der Routenplanung.

---

## 🗺️ Karte & Display
 Interaktive Map Powered by MapLibre GL JS.
 4 Layer Satellit (ESRI World Imagery), Topografisch, Street Map und Dark Map.
 UI Features
     Dark Mode Toggle für das gesamte Interface.
     Fullscreen  Hide UI Modus für maximale Kartenansicht.
     Responsive Design mit einklappbarer Sidebar (Mobile-friendly).

## 🚲 Fahrzeuge (5 Typen)
Jedes Fahrzeug verfügt über ein eigenes SVG-Icon und vordefinierte Dimensionen
 Cargo Bike Vorkonfiguriert für Lastenrad-Routing.
 Mountain Bike  Racing Bike Optimierte Profile für Sportler.
 Van Auto-Routing unter Beachtung von Fahrzeugbreite und -höhe.
 DeLorean Inklusive animiertem Feuerspur-Effekt! 🔥

## 🧭 Routing & Navigation
 BRouter API Engine 7 Profile (Racing, Trekking, MTB, Safety, Car, Eco, Walking).
 OSRM Fallback Automatischer Wechsel, falls BRouter nicht erreichbar ist.
 Smarte Features
     Bis zu 3 Alternativrouten im Vergleich.
     Dimension-Check Vermeidung von zu engen Pfaden oder niedrigen Brücken.
     Vermeidung von Autobahnen (Toggle).
 Simulation
     Animierte Turn-by-Turn Anweisungen in Echtzeit.
     Follow View (Verfolgerkamera) & Drone View (rotierende Draufsicht).
     Einstellbare Geschwindigkeit (Real-time bis Zeitraffer).

## 🔍 Suche & Wegpunkte
 Geocoding Autocomplete-Suche via Nominatim.
 Dynamic Handling Wegpunkte per Klick hinzufügen oder einfach per Drag & Drop verschieben.
 GPS Integration Mein Standort-Button zur schnellen Positionierung.

## 📍 POI & Daten (Overpass API)
 Points of Interest Ladestationen (EV), Campingplätze und Schlafplätze.
 Kultur & Tourismus 8 Kategorien (Aussichtspunkte, Schlösser, Ruinen, Museen, Kirchen, Kunstwerke etc.).
 Höhenprofil Detaillierte Anzeige von Aufstieg und Abstieg.

## 📤 Export-Optionen
Exportiere deine Route in alle gängigen Formate
 GPX (Komoot, Garmin, Strava)
 KML (Google Earth)
 TCX (Wahoo, Garmin Training)
 CSV (Tabellenkalkulation)
 Direkt-Link Öffnen der Route in Google Maps.

## 🌍 Internationalisierung
 Vollständig übersetzt in Deutsch (DE) und Englisch (EN).
 Einfacher Wechsel über SVG-Flaggen-Buttons.

---

## ⚙️ Technische Details
 Keine API-Keys benötigt Alle Datenquellen sind frei zugänglich.
 CORS-Safe Läuft problemlos auf GitHub Pages oder lokal.
 Technologien HTML5, CSS3 (FlexboxGrid), Vanilla JavaScript, MapLibre GL JS.

---

## 🚀 Deployment
Da KreherNavi eine Single-File-Lösung ist, kannst du es in Sekunden bereitstellen
1. Lade die `index.html` hoch.
2. Aktiviere GitHub Pages in den Repository-Einstellungen.
3. Fertig!