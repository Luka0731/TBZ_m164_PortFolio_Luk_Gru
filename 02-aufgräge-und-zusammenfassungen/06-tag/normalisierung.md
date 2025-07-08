# Datenbank Normalisierung (3NF)

## Ziel:
Daten aus CSV-Datei in eine normalisierte Struktur überführen:
- `tbl_Person`
- `tbl_Str` (Strasse)
- `tbl_Ort` (Ort)

## Schritte:
1. Temp-Tabelle `tbl_Adr` mit allen Feldern importieren
2. In drei Tabellen mit `INSERT INTO ... SELECT` aufteilen
3. Fremdschlüsselbeziehungen anlegen (Ort_FK, Strasse_FK etc.)
4. Redundanzen prüfen:
```sql
SELECT Ortsbezeichnung, COUNT(*) FROM tbl_Ort
GROUP BY Ortsbezeichnung HAVING COUNT(*) > 1;
```
5. Datenbereinigung via temporäre Tabelle

## Tipp:
Redundante Daten vermeiden → `GROUP BY`, `DISTINCT` prüfen!
