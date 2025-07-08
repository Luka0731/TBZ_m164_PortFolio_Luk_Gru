# Subqueries (Unterabfragen)

## Skalare Subquery
```sql
SELECT city_destination
FROM one_way_ticket
WHERE ticket_price < (
    SELECT MIN(ticket_price)
    FROM one_way_ticket
    WHERE city_destination = 'Bariloche' AND city_origin = 'Paris'
);
```
- Gibt **einen Wert** zurück (z. B. MIN, MAX)
- Vergleich mit =, <, > etc.

## Nicht-skalare Subquery
```sql
SELECT name FROM users
WHERE country IN (
    SELECT name FROM country WHERE region = 'Europa'
);
```
- Gibt **mehrere Werte** zurück
- Verwendet mit IN, EXISTS, ANY, ALL etc.

## Subquery in JOINs
```sql
SELECT c.name, o.orderdate
FROM customers c
JOIN orders o ON c.id = o.customer_id
WHERE o.orderdate IN (
    SELECT MAX(orderdate) FROM orders GROUP BY customer_id
);
```

## Wichtig
- Immer in Klammern
- Auf passende Operatoren achten
