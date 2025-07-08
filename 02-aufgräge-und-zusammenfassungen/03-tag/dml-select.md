# DML & SELECT Beispiele (Repetition)

## INSERT
```sql
INSERT INTO tbl_Mitarbeiter (ID, Vorname, Nachname, Telefonnummer)
VALUES (1, 'Hans', 'Muster', '+41 76 764 23 23');
```

## UPDATE
```sql
UPDATE tbl_Mitarbeiter
SET FS_Vorgesetzter = 3
WHERE ID = 2;
```

## DELETE
```sql
DELETE FROM tbl_Mitarbeiter
WHERE ID = 5;
```

## SELECT
```sql
-- Einfache Ausgabe
SELECT Vorname, Nachname FROM tbl_Mitarbeiter;

-- Mathematische Operationen
SELECT ROUND(1234.5, 0), POWER(2,3), PI();

-- Logik
SELECT IF(1 = TRUE, 'Ja', 'Nein') AS Ergebnis;

-- JOIN
SELECT t.ID_Tour, o1.Ort AS Start, o2.Ort AS Ziel
FROM tbl_Tour t
JOIN tbl_Ort o1 ON t.FK_Startort = o1.ID
JOIN tbl_Ort o2 ON t.FK_Zielort = o2.ID;
```
