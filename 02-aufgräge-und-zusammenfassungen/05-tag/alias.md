# SELECT ALIAS in SQL

Aliase helfen bei besserer Lesbarkeit von SQL-Abfragen.

```sql
SELECT name AS Vorname FROM kunden;
SELECT k.name, b.titel FROM kunden k JOIN bestellungen b ON k.id = b.kunden_id;
```

- `AS` für Spaltenalias
- Tabellenalias z. B. `kunden k` muss durchgehend in der Abfrage verwendet werden
