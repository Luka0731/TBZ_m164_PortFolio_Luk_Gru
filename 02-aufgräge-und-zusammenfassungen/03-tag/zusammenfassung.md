# Tag 3 – Zusammenfassung

## Thema: Datenbanken erstellen und Daten einfügen

### SQL-Datentypen (Repetition M162)
Heute wurden die verschiedenen Datentypen in MariaDB/MySQL repetiert. Die wichtigsten:

- **INT / INTEGER**: Ganze Zahlen
- **UNSIGNED INT**: Natürliche Zahlen (keine negativen Werte)
- **DECIMAL(M,D)**: Festkommazahlen, z. B. `DECIMAL(6,2)` für Geldbeträge
- **ENUM**: Aufzählungstypen
- **BOOLEAN**: TRUE oder FALSE
- **CHAR(n)**: Zeichenkette fester Länge
- **VARCHAR(n)**: Zeichenkette variabler Länge
- **DATE / TIME / DATETIME / TIMESTAMP**: Zeitformate
- **BLOB**: Binäre Daten (z. B. Bilder)
- **JSON**: Strukturierte Daten

### Mehrfachbeziehungen
Tabellen können mehrere Beziehungen zueinander haben, z. B. Start-Ort, Ziel-Ort, Via-Orte zwischen Fahrten und Orten. Dies erfordert eine saubere Modellierung mit Transformationstabellen und sinnvollen Rollenbezeichnungen.

### Rekursion / Einfache Hierarchie
Rekursion bedeutet, dass ein Datensatz in Beziehung zu sich selbst steht (z. B. Mitarbeiter mit Vorgesetzten). Wenn mehrere Vorgesetzte möglich sind, muss eine Zwischentabelle (Transformationstabelle) verwendet werden.

### Stücklistenproblem
Ein klassisches Rekursionsbeispiel: Ein Produkt besteht aus mehreren Komponenten, die ihrerseits ebenfalls Produkte sein können. Die Modellierung benötigt eine zusätzliche Tabelle zur Verwaltung der Zusammensetzungen.

### DML-Repetition (INSERT, UPDATE, DELETE)
Es wurden einfache DML-Befehle angewendet, um Daten in Tabellen einzufügen und zu verändern. Beispiel:

```sql
INSERT INTO tbl_Mitarbeiter (ID, Vorname, Nachname, Telefonnummer)
VALUES (1, 'Hans', 'Muster', '+41 76 764 23 23');

UPDATE tbl_Mitarbeiter
SET FS_Vorgesetzter = 3
WHERE ID = 2;

DELETE FROM tbl_Mitarbeiter
WHERE ID = 5;
```

### SELECT-Repetition (inkl. Funktionen und JOINs)
Anwendung von `SELECT` zur Datenabfrage, inkl. Mathefunktionen (`ROUND()`, `PI()`, `POWER()`), Logik (`IF()`), Bedingungen (`WHERE`) und Mehrtabellenabfragen (`JOIN`).

---

Weitere Infos in SQL-Dateien, Screenshots oder Datenbank-Dumps.
