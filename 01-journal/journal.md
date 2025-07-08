
# Journal

## Inhaltsverzeichnis

* [Tag 1 – 13.05.2025](#tag-1---13052025)
* [Tag 2 – 20.05.2025](#tag-2---20052025)
* [Tag 3 – 27.05.2025](#tag-3---27052025)
* [Tag 4 – 03.06.2025](#tag-4---03062025)
* [Tag 5 – 10.06.2025](#tag-5---10062025)
* [Tag 6 – 17.06.2025](#tag-6---17062025)
* [Tag 7 – 24.06.2025](#tag-7---24062025)
* [Tag 8 – 01.07.2025](#tag-8---01072025)

---

### Tag 1 - 13.05.2025

Heute war der erste Tag des Modules. Wir bekamen eine kurze Einführung, worum es in diesem Modul geht und wie es ablaufen wird. Für den Unterricht heute bekamen wir Zeit, alte Themen zu rezitieren, wie z. B. ERD, ERM und physikalisches Layer. Zu Anfang hatten wir ein kurzes Quiz im Plenum. Dann mussten wir eine Datenbank für einen Zugtourplaner erstellen. Ich setzte mich mit Elif zusammen und wir lösten die Aufgabe gemeinsam. Zuerst überlegten wir uns, was für Entities und Attribute es braucht und schrieben daraufhin eine Mischung zwischen ERM und ERD. Mit MySQL digitalisierten wir das ERM und generierten daraus die Datenbank.

Das Projekt lief ohne Schwierigkeiten und ich konnte einen guten Start in den Tag finden. Heute schauten wir ebenfalls die Git-Unterlagen zu diesem Modul an. Ich konnte mir aufgrund von Installationen nicht alle anschauen. Ich werde das aber bis zum nächsten Mal nachholen.

---

### Tag 2 - 20.05.2025

Heute erstellten wir das physische Datenmodell basierend auf unserem logischen ERD. Ich lernte, wie man Primärschlüssel, Fremdschlüssel und passende Datentypen zuweist. Danach führten wir Forward Engineering in MySQL Workbench durch, um unsere Tabellen in der Datenbank zu generieren.

Zusätzlich führten wir Datenbankabfragen durch (SELECT, INSERT, UPDATE). Ich konnte mein Wissen aus früheren Modulen anwenden und vertiefen.

---

### Tag 3 - 27.05.2025

Wir behandelten heute rekursive Beziehungen sowie die Umsetzung komplexerer Kardinalitäten. Dabei ging es z. B. um Selbstbeziehungen wie „Mitarbeiter leitet Mitarbeiter“. Wir lernten, wie man das im ERD abbildet und in SQL umsetzt.

Zusätzlich bearbeiteten wir Aufträge zur Umsetzung dieser Beziehungen mit JOINs. Es war teilweise herausfordernd, aber durch Partnerarbeit gut lösbar.

---

### Tag 4 - 03.06.2025

Heute ging es um Constraints (NOT NULL, UNIQUE) und wie man sie bei Beziehungen einsetzt. Ich lernte die vier Beziehungstypen mit Einschränkungen im physischen Modell kennen: 1:1, 1:n, m:n und rekursiv. Danach erzeugten wir SQL-Skripte über Forward Engineering und analysierten, wie Constraints im SQL umgesetzt werden.

Zusätzlich wiederholten wir JOIN-Abfragen und Mengenlehre (∪, ∩, \, ∈). Das half, SQL-Abfragen besser zu verstehen.

---

### Tag 5 - 10.06.2025

Der Fokus lag heute auf Subselects (Subqueries). Ich lernte den Unterschied zwischen skalaren und nicht-skalaren Unterabfragen und setzte verschiedene SELECT-Abfragen mit Subqueries um.

Am Nachmittag machten wir einen ersten Bulk-Import mit `LOAD DATA INFILE`. Ich musste dabei auf Zeichensatz, Spaltenreihenfolge und Datumsformate achten. Teilweise gab es Probleme mit NULL-Werten und Constraints, die ich dann mit Anpassungen im SQL lösen konnte.

---

### Tag 6 - 17.06.2025

Heute lernten wir weiterführende Techniken für `LOAD DATA LOCAL INFILE`, z. B. das Auslassen von Spalten, Setzen von Default-Werten oder die Umwandlung von Werten mit `CASE`. Danach normalisierten wir eine Adresse-Datenbank bis in die 3. Normalform (tbl_Ort, tbl_Str, tbl_Person).

Ein Highlight war der Vergleich der normalisierten Tabellen mit der Originaltabelle via SELECT … JOIN. Am Schluss führten wir INSERT SELECTs durch, um Daten strukturiert weiterzuverarbeiten.

---

### Tag 7 - 24.06.2025

Der Tag startete mit einer Wiederholung zu Backup-Strategien (Full, Inkrementell, Differentiell) und verschiedenen Tools wie `mysqldump` und `phpMyAdmin`. Ich lernte, wie wichtig regelmäßige Sicherungen sind.

Danach arbeiteten wir weiter an der Aufgabe „Freifächer“. Ich normalisierte die Tabelle aus Excel, überführte die Daten in eine relationale DB und führte Datenbereinigungen durch. Danach wurden Abfragen erstellt: Teilnehmer pro Fach, Verteilung nach Klasse etc. Zum Schluss wurde ein Backup der DB gemacht.

---

### Tag 8 - 01.07.2025

Am letzten Tag importierte ich Daten aus einer OpenData-Quelle. Zur Auswahl standen z. B. Steuerdaten Zürich oder Bildungsdaten BFS. Ich entschied mich für die Steuerdaten.

Nach dem Import bereinigte ich die Daten, erstellte ein physisches ERD, normalisierte die Tabelle und beantwortete Auswertungsfragen mit SQL (z. B. „Welches Quartier hat den höchsten Medianwert?“). Am Ende erstellte ich ein Backup der Steuerdatenbank.

---
