# Beziehungstypen in relationalen Datenbanken

## 1. Mehrfachbeziehungen
Zwei Tabellen sind mehrfach miteinander verbunden – z. B. Orte (Start, Ziel, Zwischenhalt) und Touren. Jede Verbindung hat eine eigene Rolle und benötigt u. U. eine eigene Zwischentabelle mit klar benannten Fremdschlüsseln.

## 2. Rekursion (strenge Hierarchie)
Eine Tabelle verweist innerhalb auf sich selbst. Beispiel: Mitarbeitende mit Vorgesetzten. Fremdschlüssel verweist auf Primärschlüssel derselben Tabelle.

```sql
ALTER TABLE tbl_Mitarbeiter
ADD COLUMN FS_Vorgesetzter INT,
ADD CONSTRAINT fk_vorgesetzter
FOREIGN KEY (FS_Vorgesetzter) REFERENCES tbl_Mitarbeiter(ID);
```

## 3. Einfache Hierarchie mit Zwischentabelle
Bei einer Netzwerkstruktur mit mehreren Vorgesetzten braucht es eine separate Transformationstabelle, z. B. tbl_Hierarchie.

```sql
CREATE TABLE tbl_Hierarchie (
  FK_ist_Vorg_von INT,
  FK_ist_MA_von INT,
  Bemerkung TEXT,
  FOREIGN KEY (FK_ist_Vorg_von) REFERENCES tbl_Mitarbeiter(ID),
  FOREIGN KEY (FK_ist_MA_von) REFERENCES tbl_Mitarbeiter(ID)
);
```

## 4. Stücklistenproblem
Produkte bestehen aus Unterkomponenten, die selbst Produkte sein können. Modellierung mittels Rekursion und Stücklistentabelle:

```sql
CREATE TABLE tbl_Stueckliste (
  FK_Aggregat INT,
  FK_Komponente INT,
  Menge INT,
  FOREIGN KEY (FK_Aggregat) REFERENCES tbl_Produkt(ID),
  FOREIGN KEY (FK_Komponente) REFERENCES tbl_Produkt(ID)
);
```
