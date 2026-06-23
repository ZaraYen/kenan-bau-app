# Kenan Bau — Zeiterfassung App

## Projektübersicht

Web-basierte Zeiterfassungs-App für Kenan Straßen & Tiefbau GmbH. Läuft vollständig im Browser, keine Build-Pipeline erforderlich.

## Technologie-Stack

- **Frontend:** Vanilla HTML/CSS/JavaScript (Single-File-App)
- **Datenbank:** Supabase (PostgreSQL-Backend via REST-API)
- **Excel-Export:** SheetJS (xlsx)
- **Schriftart:** DM Sans, DM Mono (Google Fonts)
- **Deployment:** IONOS Webhosting via FTP

## Projektstruktur

```
Stundebau_App/
├── index_v4_1.html          # Haupt-App (gesamte Anwendung in einer Datei)
├── 400dpiLogoCropped.jpg    # Firmenlogo
├── .github/
│   └── workflows/
│       └── deploy.yml       # GitHub Actions: automatisches FTP-Deployment auf IONOS
└── CLAUDE.md                # Diese Datei
```

## GitHub Repository

- **URL:** https://github.com/ZaraYen/kenan-bau-app
- **Branch:** `main` → löst automatisches Deployment aus

## Deployment (GitHub Actions)

Bei jedem Push auf `main` werden die Dateien automatisch per FTP auf IONOS hochgeladen.

**Erforderliche GitHub Secrets** (unter Settings → Secrets → Actions eintragen):

| Secret | Beschreibung |
|--------|-------------|
| `FTP_SERVER` | IONOS FTP-Hostname (z.B. `ftp.kenanstrassenbau.de`) |
| `FTP_USERNAME` | FTP-Benutzername |
| `FTP_PASSWORD` | FTP-Passwort |

## App-Funktionen

- Mitarbeiter-Zeiterfassung (Arbeitsbeginn / -ende / Pause)
- Admin-Bereich für Vorgesetzte
- Mehrsprachig: Deutsch / Türkisch
- Excel-Export der Stundenzettel
- Mobile-optimiert (PWA-fähig)
- Offline-tolerant mit Supabase-Sync

## Entwicklung

Da die App eine einzelne HTML-Datei ist, reicht ein einfacher Webserver oder direktes Öffnen im Browser:

```bash
# Mit VS Code Live Server Extension
# oder:
npx serve .
```

Änderungen direkt in `index_v4_1.html` vornehmen — kein Build-Schritt nötig.
