# Beziehungen & Constraints in SQL

## Erstellung mit `ALTER TABLE`

```sql
ALTER TABLE DetailTabelle
  ADD CONSTRAINT FK_Name FOREIGN KEY (Fremdschlüssel)
  REFERENCES MasterTabelle (Primärschlüssel);
```

Beispiel für UNIQUE-Constraint:

```sql
ALTER TABLE tbl_Fahrer
  ADD CONSTRAINT fk_ausweis
  FOREIGN KEY (FS_Ausweis)
  REFERENCES tbl_Ausweis(ID),
  ADD UNIQUE (FS_Ausweis);
```

## Analysefragen

- Warum werden bei Fremdschlüsseln automatisch Indizes gesetzt? → Für Performanz beim Join
- Was passiert bei `NULL`-Werten oder nicht existierenden FS? → Fehler bei aktivem Constraint
