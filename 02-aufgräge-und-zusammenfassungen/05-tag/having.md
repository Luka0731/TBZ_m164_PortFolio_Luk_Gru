# HAVING-Klausel in SQL

Wird zur Filterung aggregierter Werte (nach GROUP BY) verwendet.

```sql
SELECT kunde_id, SUM(betrag)
FROM bestellungen
GROUP BY kunde_id
HAVING SUM(betrag) > 500;
```

- **WHERE**: Filter VOR der Gruppierung
- **HAVING**: Filter NACH der Gruppierung
