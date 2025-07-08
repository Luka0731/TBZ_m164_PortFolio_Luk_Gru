# Aggregatsfunktionen in SQL

| Funktion | Beschreibung |
|----------|--------------|
| COUNT(*) | Anzahl aller Zeilen |
| COUNT(attr) | Anzahl NICHT-NULL-Werte |
| SUM(attr) | Summe |
| AVG(attr) | Durchschnitt |
| MIN(attr) | Kleinster Wert |
| MAX(attr) | Grösster Wert |

```sql
SELECT COUNT(*) FROM kunden;
SELECT AVG(preis) FROM artikel;
```
