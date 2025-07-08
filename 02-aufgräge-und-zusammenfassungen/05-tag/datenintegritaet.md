# Datenintegrität und Löschen in DBs

## Vier Aspekte der Datenintegrität
1. **Entitätsintegrität** – Eindeutige, konsistente Datensätze (z. B. Primärschlüssel)
2. **Referentielle Integrität** – Fremdschlüssel müssen gültig sein
3. **Bereichswertintegrität** – Richtiges Datentypen-Format
4. **Benutzerdefinierte Integrität** – Z. B. positive Zahlen, E-Mail-Format

## Fremdschlüssel-Optionen beim Löschen

| Option | Wirkung |
|--------|---------|
| NO ACTION | Löschen nicht erlaubt, wenn FK existiert |
| RESTRICT | Wie NO ACTION, aber strikter |
| CASCADE | Löscht verbundene Daten in FK-Tabellen |
| SET NULL | Setzt FK-Feld auf NULL, wenn erlaubt |
| SET DEFAULT | Nur bei Default-Wert nutzbar |

**Best Practice:** Anstatt echte Löschungen vorzunehmen, z. B. Datensätze als „inaktiv“ markieren.
