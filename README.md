# Werkstattatlas Scraper

Scrapt alle Eisenbahn-Werkstätten von [werkstattatlas.info](http://www.werkstattatlas.info/unternehmen/283-wartung_instandhaltung_service.html) und speichert sie als strukturiertes JSON.

## Daten

- **`data/werkstaetten.json`** — Alle Werkstätten mit Name, Adresse, Telefon, Website
- **`data/stats.md`** — Aktuelle Statistiken

## Schema

```json
{
  "id": 6874,
  "name": "DB Fernverkehr AG",
  "url": "http://www.werkstattatlas.info/unternehmen/6874-db-fernverkehr-ag.html",
  "workshop_name": "Werk Berlin-Rummelsburg",
  "street": "Saganer Straße 3",
  "postal_code": "10317",
  "city": "Berlin",
  "country_code": "DE",
  "country": "Deutschland",
  "phone": "+49 30 297-18792",
  "fax": "+49 30 297-18791",
  "website": "https://..."
}
```

## Automatische Aktualisierung

GitHub Actions scrapt wöchentlich (Montag 06:00 UTC) und committet Änderungen automatisch.

Manuell: `Actions` → `Scrape Werkstattatlas` → `Run workflow`

## Lokal ausführen

```bash
python scraper.py              # Mit Detail-Seiten (langsam, ~400 Requests)
python scraper.py --no-details # Nur Übersichtsseiten (schnell, 28 Requests)
```

## Quelle

Daten von [werkstattatlas.info](http://www.werkstattatlas.info) — ein Verzeichnis europäischer Eisenbahn-Werkstätten.
