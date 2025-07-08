# Tag 8 – Daten normalisiert einbinden & Opendata

## Teil 1: Weiterarbeit Freifächer

Heute wurden die Arbeiten zur Freifächer-Datenbank fortgesetzt. Der Fokus lag auf der vollständigen Normalisierung, dem Import grösserer Testdatenmengen und erweiterten SQL-Abfragen.

- Datenbasis wurde nochmals geprüft und in die 1.NF bis 3.NF überführt.
- CSV-Dateien wurden mit 290 generierten Schüler*innen ergänzt.
- Überprüfung der Datenqualität und Sicherstellung referentieller Integrität.
- Erweiterte SELECT-Abfragen implementiert (JOIN, COUNT, WHERE, LIKE usw.).
- Export von Ergebnissen via `SELECT INTO OUTFILE`.
- Backup der fertigen DB erstellt.

## Teil 2: Arbeiten mit Opendata

Wir haben begonnen, Open Government Data (OGD) aus der Schweiz zu analysieren und in eigene Datenbanken zu überführen. Es standen mehrere Themen zur Auswahl:

- Steuerdaten Stadt Zürich
- Bildungsdaten vom Bundesamt für Statistik (BFS)
- Eigene gewählte Quelle (OpenData Swiss, Open Access, etc.)

Daten wurden analysiert, normalisiert und importiert. Erste Auswertungen (GROUP BY, MAX/MIN, WHERE) wurden vorgenommen.

## Learnings

- Umgang mit grossen CSV-Dateien
- Umgang mit Opendata-Formaten und deren Struktur
- Aufbau skalierbarer Datenstrukturen
- Erstellen produktionsnaher SQL-Dumps & Backups