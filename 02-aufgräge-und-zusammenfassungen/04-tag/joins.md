# JOINs in SQL (Repetition DQL)

## Grundlegende JOINs

```sql
-- INNER JOIN
SELECT * FROM A
JOIN B ON A.id = B.a_id;

-- LEFT JOIN
SELECT * FROM A
LEFT JOIN B ON A.id = B.a_id;

-- RIGHT JOIN
SELECT * FROM A
RIGHT JOIN B ON A.id = B.a_id;
```

## Anwendung bei Tourenplaner

```sql
SELECT t.TourNummer, o1.Ort AS Start, o2.Ort AS Ziel
FROM tbl_Tour t
JOIN tbl_Ort o1 ON t.FK_Startort = o1.ID
JOIN tbl_Ort o2 ON t.FK_Zielort = o2.ID;
```
