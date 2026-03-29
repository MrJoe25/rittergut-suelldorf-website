# Rittergut Sülldorf — Website

Offizielle Website des Ritterguts Sülldorf, einem landwirtschaftlichen Familienbetrieb der Familie von Alvensleben in der Magdeburger Börde (Sachsen-Anhalt). Die Website präsentiert den Betrieb, seine Geschichte, die Region sowie ein historisches Bildarchiv.

**Live-URL:** *(wird nach Deployment eingetragen)*

---

## Inhalt

- [Über das Projekt](#über-das-projekt)
- [Ordnerstruktur](#ordnerstruktur)
- [Technologien](#technologien)
- [Lokale Entwicklung](#lokale-entwicklung)
- [Deployment](#deployment)
- [Kontaktformular](#kontaktformular)
- [Bilder & Assets](#bilder--assets)

---

## Über das Projekt

Die Website ist eine einseitige statische HTML-Seite (Single Page) auf Deutsch. Sie enthält folgende Abschnitte:

| Abschnitt | Beschreibung |
|---|---|
| **Startseite / Hero** | Begrüßung mit wichtigen Kenndaten (235 ha, seit 1885, Schwarzerde) |
| **Der Betrieb heute** | Aktuelle Bewirtschaftung, Anbaukulturverteilung, Betriebsstatistiken |
| **Die Magdeburger Börde** | Geographische und bodenkundliche Informationen zur Region |
| **Fast 1000 Jahre Sülldorf** | Historische Zeitleiste des Guts von den Anfängen bis zur Rückkehr nach der Wende |
| **Bildarchiv** | Historische Fotografien (1890–1996) mit Lightbox-Viewer |
| **Kontakt** | Kontaktformular (via Formspree) und Impressum / Datenschutzhinweis |

---

## Ordnerstruktur

```
rittergut-suelldorf-website/
│
├── index.html              # Gesamte Website (HTML, CSS und JavaScript in einer Datei)
│
├── images/                 # Alle Bilder der Website
│   ├── altes_gutshaus_1930.jpg       # Altes Gutshaus, ca. 1930
│   ├── gutshaus_1935.jpg             # Gutshaus, 1935
│   ├── hoflageplan_1933.png          # Hoflageplan, 1933
│   ├── ingeborg_joachim_1996.jpg     # Ingeborg & Joachim, 1996
│   ├── joachim_1899_1942.jpg         # Joachim von Alvensleben, 1899–1942
│   ├── porzellanteller_1890.jpg      # Porzellanteller mit Wappen, 1890
│   ├── postkarte_suelldorf.jpg       # Historische Postkarte Sülldorf
│   └── toreinfahrt_1935.jpg          # Toreinfahrt, 1935
│
└── README.md               # Diese Datei
```

### Wichtiger Hinweis zur Struktur

Die gesamte Website — HTML-Markup, CSS-Styling und JavaScript — ist bewusst in der einzigen Datei `index.html` zusammengefasst. Es gibt **keine Build-Tools, kein Framework und keine Abhängigkeiten**. Das vereinfacht Hosting und Wartung erheblich.

---

## Technologien

- **HTML5** — Semantisches Markup
- **CSS3** — Inline im `<style>`-Block
  - CSS Custom Properties (Variablen) für das Farbsystem
  - CSS Grid und Flexbox für das Layout
  - Responsive Design via Media Queries und `clamp()`
- **JavaScript (Vanilla)** — Inline im `<script>`-Block
  - Navigation / Scroll-Effekte
  - Mobiles Hamburger-Menü
  - Lightbox-Bildviewer
  - Intersection Observer API für Scroll-Animationen
  - Formularversand via Fetch API
- **Google Fonts** — Cormorant Garamond, Source Serif 4, DM Sans
- **Formspree** — Externer Dienst für den E-Mail-Versand des Kontaktformulars

---

## Lokale Entwicklung

Da die Website keine Build-Tools benötigt, reicht es, die `index.html` direkt im Browser zu öffnen:

```bash
# Option 1: Direkt öffnen
open index.html

# Option 2: Lokaler Entwicklungsserver (empfohlen, z. B. mit Python)
python3 -m http.server 8080
# Dann im Browser: http://localhost:8080

# Option 3: Mit Node.js / npx
npx serve .
# Dann im Browser: http://localhost:3000
```

---

## Deployment

Die Website kann auf jedem statischen Hosting-Dienst deployed werden, da sie keine serverseitige Verarbeitung benötigt. Empfehlungen:

| Dienst | Hinweise |
|---|---|
| **GitHub Pages** | Kostenlos, direkt aus diesem Repository |
| **Netlify** | Einfaches Drag-and-Drop oder Git-Integration |
| **Vercel** | Automatisches Deployment bei Push auf `main` |
| **Eigener Webserver** | Einfach `index.html` und `images/`-Ordner hochladen (FTP/SFTP) |

### GitHub Pages aktivieren

1. Repository-Einstellungen öffnen: `Settings → Pages`
2. Branch `main` und Root-Verzeichnis `/` auswählen
3. Speichern — die Website ist dann unter `https://<username>.github.io/rittergut-suelldorf-website/` erreichbar

---

## Kontaktformular

Das Kontaktformular verwendet [Formspree](https://formspree.io/). Die Formular-Endpunkt-URL ist direkt in `index.html` hinterlegt (`action`-Attribut des `<form>`-Elements).

Falls die Formular-ID geändert werden muss, die entsprechende Zeile in `index.html` anpassen:

```html
<form action="https://formspree.io/f/XXXXXXXX" method="POST">
```

---

## Bilder & Assets

Alle Bilder befinden sich im Ordner `images/`. Es handelt sich ausschließlich um historisches Familienmaterial. Bei Änderungen oder Ergänzungen:

- Neue Bilder in den `images/`-Ordner legen
- Dateinamen ohne Leerzeichen und Sonderzeichen (Kleinbuchstaben, Unterstriche)
- Im HTML die entsprechenden `<img src="images/dateiname.jpg">`-Pfade eintragen

---

## Git-Workflow

```bash
# Repository klonen
git clone https://github.com/MrJoe25/rittergut-suelldorf-website.git
cd rittergut-suelldorf-website

# Änderungen vornehmen, dann committen
git add .
git commit -m "Beschreibung der Änderung"
git push origin main
```

Bitte direkt auf `main` entwickeln, da es keine komplexe Build-Pipeline gibt. Für größere Änderungen empfiehlt sich ein eigener Feature-Branch und anschließend ein Pull Request.

---

*Familie von Alvensleben — Rittergut Sülldorf, Magdeburger Börde*
