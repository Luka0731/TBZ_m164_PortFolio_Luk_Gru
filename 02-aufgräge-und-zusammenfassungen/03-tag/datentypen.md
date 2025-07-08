# SQL-Datentypen Übersicht (MariaDB / MySQL)

| Datentyp | Beschreibung | Beispiel | Bemerkung |
|----------|--------------|----------|-----------|
| INT / INTEGER | Ganze Zahlen | 42 | Standard für IDs |
| UNSIGNED INT | Natürliche Zahlen | 10 | Keine negativen Werte |
| DECIMAL(M,D) | Festkommazahlen | DECIMAL(6,2): 1234.56 | Für Geldbeträge |
| ENUM | Aufzählungstyp | ENUM('männlich', 'weiblich') | Werte sind festgelegt |
| BOOLEAN | Wahr/Falsch | TRUE / FALSE | 0 = FALSE, 1 = TRUE |
| CHAR(n) | Zeichen fester Länge | CHAR(3): 'ABC' | Fixe Länge, immer gleich lang |
| VARCHAR(n) | Zeichen variabler Länge | VARCHAR(255): 'Text' | Häufig verwendet |
| DATE / TIME / DATETIME / TIMESTAMP | Zeitangaben | '2025-07-08' | Verschiedene Zeitformate |
| BLOB | Binäre Daten | z. B. Bild | Binary Large Object |
| JSON | Strukturierte Daten | '{"id":1}' | Seit MySQL 5.7 |

Dies ist eine kompakte Übersicht der häufigsten Datentypen.
