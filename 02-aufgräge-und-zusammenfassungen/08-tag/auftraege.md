# Tag 8 – Aufgabenübersicht

## Aufgabe 1: DB_Freifächer erneut umsetzen

1. Normalform (1NF) sicherstellen, Daten als CSV exportieren
2. Logisches & Physisches ERD erstellen
3. SQL-DDL generieren (Forward Engineering)
4. Daten importieren via `LOAD DATA LOCAL INFILE`
5. Daten bereinigen
6. Vergleich mit SELECT-Query-Ausgaben aus CSV
7. 290 Schülerdatensätze generieren & importieren
8. Abfragen:
   - Teilnehmerzahl bei Inge Sommer
   - Schüleranzahl pro Klasse in Freifächern
   - Schüler*innen im "Chor" oder "Elektronik"
   - Ergebnis in Datei exportieren (`SELECT INTO OUTFILE`)
9. Backup der Datenbank erstellen

## Aufgabe 2: Opendata importieren

Wähle eines der folgenden Themen:

### Option A: Steuerdaten Stadt Zürich

- Download CSV von der Stadt Zürich
- Normalisierung & Import in DB
- Analyse zu _p25, _p50, _p75
- Abfragen zu höchstem/niedrigstem Steuereinkommen
- Backup

### Option B: Bildungsdaten vom BFS

- Excel analysieren & als CSV exportieren
- Datenbankmodell erstellen & importieren
- Abfragen:
  - Unter dem OECD-Mittel
  - Höchste tertiäre Ausbildung
  - Grösste jährliche Steigerung

### Option C: Eigene Opendata-Quelle

- Download geeigneter OGD
- Normalisieren, importieren, analysieren
- Backup

## Hinweise:

- Ablage aller Resultate im Portfolio (Scripte & Resultate)
- Queries dokumentieren & kommentieren
- Backup-Skripte prüfen