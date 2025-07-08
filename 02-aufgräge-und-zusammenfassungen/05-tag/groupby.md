# GROUP BY in SQL

```sql
SELECT kunde_id, SUM(betrag)
FROM bestellungen
GROUP BY kunde_id;
```

- Gruppiert Zeilen anhand Spalte(n)
- Wird zusammen mit Aggregatsfunktionen verwendet
