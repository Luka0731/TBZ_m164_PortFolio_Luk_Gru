# Tag 7 – Datensicherung und Normalisierung

## Thema 1: Datensicherung / DB-Backup

- **Warum Backups wichtig sind**: Datenverlust kann nicht nur durch Hackerangriffe passieren, sondern oft durch Benutzerfehler oder Hardwareausfall.
- **Backup-Arten**:
  - **Voll-Backup**: Alles wird gesichert. Hoher Speicherverbrauch.
  - **Differenzielles Backup**: Nur Änderungen seit letztem Voll-Backup. Schneller, braucht aber noch das letzte Voll-Backup zur Wiederherstellung.
  - **Inkrementelles Backup**: Nur Änderungen seit letzter Sicherung. Speicher- und zeiteffizient, aber alle Dateien müssen zur Wiederherstellung vorhanden sein.
- **Backup-Tools**:
  - `mysqldump`, `phpMyAdmin`, `HeidiSQL`, `BigDump`, `Mariabackup`
- **Backup-User**:
  ```sql
  GRANT RELOAD, PROCESS, LOCK TABLES, REPLICATION CLIENT ON *.* TO 'backupuser'@'localhost' IDENTIFIED BY 'backup123';
  ```

## Thema 2: Datenbank "Freifächer"

- Einbindung von CSV-Daten in eine normalisierte Datenbank
- Erstellung von ERD (logisch und physisch)
- Datenbereinigung und Validierung (FK, Redundanz, etc.)
- Automatisierte Testdatengenerierung (290 Schüler:innen)
- Nutzung von `SELECT INTO OUTFILE` zum Exportieren

