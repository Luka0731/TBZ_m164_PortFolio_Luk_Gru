# LOAD DATA LOCAL INFILE (CSV-Import)

## Syntax
```sql
LOAD DATA LOCAL INFILE 'C:/Pfad/datei.csv'
INTO TABLE tbl_ziel
CHARACTER SET utf8mb4
FIELDS TERMINATED BY ',' 
LINES TERMINATED BY '\r\n'
IGNORE 1 LINES
(ID, Name, @Datum, Wert)
SET Geburtsdatum = STR_TO_DATE(@Datum, '%d.%m.%Y');
```

## Optionen
- `IGNORE 1 LINES`: Ignoriert Spaltenüberschriften
- `@Variable`: Zwischenspeicher für Transformation
- `STR_TO_DATE()`: Datum konvertieren
- `CASE`: Werte umwandeln

## Fehlervermeidung
- `SET FOREIGN_KEY_CHECKS=0;`
- Zeichensatz prüfen
- Pfadformate korrekt angeben (Linux-Style `/`)
