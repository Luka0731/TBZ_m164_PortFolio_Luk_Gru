# Tag 5 – Zusammenfassung

## Themenübersicht:
- Löschen in professionellen Datenbanken
- Vier Regeln der Datenintegrität
- Fremdschlüsselverhalten bei ON DELETE
- SELECT-Alias zur Lesbarkeit von Abfragen
- Aggregatsfunktionen: COUNT, SUM, AVG, MIN, MAX
- GROUP BY & HAVING zur Datenverdichtung

## Highlights
Wir haben gelernt, warum echtes Löschen von Daten (DELETE) in professionellen Anwendungen selten verwendet wird. Stattdessen nutzt man oft Statuskennzeichen wie "inaktiv", um Daten historisch korrekt zu speichern.

Ein wichtiges Thema war die **referentielle Integrität** – und wie die verschiedenen FK-Optionen (NO ACTION, CASCADE, SET NULL etc.) kontrollieren, was beim Löschen passiert.

Mit Aggregatsfunktionen konnten wir erste Analysen wie Summen oder Durchschnittswerte durchführen, kombiniert mit `GROUP BY` und `HAVING`, um strukturierte Auswertungen zu erstellen. Besonders der Unterschied zwischen `WHERE` und `HAVING` war entscheidend für korrektes Filtern.

Auch das Arbeiten mit **Spalten- und Tabellenaliasen** wurde repetiert.
