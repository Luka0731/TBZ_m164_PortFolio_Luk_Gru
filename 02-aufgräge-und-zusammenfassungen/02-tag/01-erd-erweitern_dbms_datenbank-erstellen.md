# ERd Erweitern, DBMS und Datenbanken Erstellen

## Inhaltsverzeichnis

* [Generalisierung / Spezialisierung](generalisierung-/-spezialisierung)
* [Beziehungsarten: Indentifying / Non-Identifying Relationship](#beziehungsarten:-indentifying-/-non-identifying-relationship)
* [Kombinationen von Vererbung und Beziehungstypen](#kombinationen-von-vererbung-und-beziehungstypen)
* [DBMS](#dbms)

---

### Generalisierung / Spezialisierung

Auch in Datenbanken gibt es eine Art von Vererbung. Die generalistische Tabelle ist die Master Class und die spezialisierte Tabelle ist die Childe Tabelle. Die Verwendung von Generalisierung und Spezialisierung vermeidet Redudanzen und verbessert die Datenstruktur.

sql´´´
    -- Generalisierte Tabelle
    CREATE TABLE person (
        person_id INT PRIMARY KEY,
        name VARCHAR(100),
        geburtsdatum DATE
    );

    -- Spezialisierte Tabelle
    CREATE TABLE student (
        person_id INT PRIMARY KEY,
        matrikelnummer VARCHAR(20),
        studiengang VARCHAR(100),
        FOREIGN KEY (person_id) REFERENCES person(person_id)
    );

    -- Spezialisierte Tabelle
    CREATE TABLE dozent (
        person_id INT PRIMARY KEY,
        dozentennummer VARCHAR(20),
        fachgebiet VARCHAR(100),
        FOREIGN KEY (person_id) REFERENCES person(person_id)
    );
´´´

### Umsetzung davon in MySQL 

![Teilabhängigkeit](c:\Users\lukag\Documents\GitHub\TBZ_m164_PortFolio_Luk_Gru\ki-antwort-generalisierung-und-spezifizierung.jpg) 

---

## Beziehungsarten: Indentifying / Non-Identifying Relationship

Bei Beziehungen zwischen zwei Tabellen kann man zwischen zwein Beziehungsarten unterscheiden. In den Beispilen die gezeigt werden ist es immer zwischen einer Child- und einer Parent-Tabelle. Dabei besitzt die Child-Tabelle den FK. Beziehungsarten exestieren auch bei "has-a" Beziehungen, wozu auch Beispiele im  [nächsten Kapitel](#kombinationen-von-vererbung-und-beziehungstypen) stehen.

### Indentifying (Strong)

In dieser Beziehung kann die Childe Tabelle ohne die Parent Tabelle nicht exestieren. Der Foren Key ist ein teil des Primary Keys.
![Identifying Beziehunngstyp](https://gitlab.com/ch-tbz-it/Stud/m164/-/raw/main/2.Tag/media/Identifying.png)


### Non-Identifying (Weak)

In dieser Beziehun kann die Childe Tabelle ohne die Parent Tabelle exestieren. Der Foren Key ist komplet seperat zum Primary Key.
![Non-Identifying Beziehunngstyp](https://gitlab.com/ch-tbz-it/Stud/m164/-/raw/main/2.Tag/media/Non-Identifying.png)

---

## Kombinationen von Vererbung und Beziehungstypen

### 1. has-a + Identifying Relationship
sql´´´
    CREATE TABLE bestellung (
        bestell_id INT PRIMARY KEY
    );

    CREATE TABLE bestellposition (
        bestell_id INT,
        position_nr INT,
        artikel TEXT,
        PRIMARY KEY (bestell_id, position_nr),
        FOREIGN KEY (bestell_id) REFERENCES bestellung(bestell_id)
    );
´´´

### 2. has-a + Non-Identifying Relationship
sql´´´
    CREATE TABLE abteilung (
        abteilung_id INT PRIMARY KEY
    );

    CREATE TABLE mitarbeiter (
        mitarbeiter_id INT PRIMARY KEY,
        name TEXT,
        abteilung_id INT,
        FOREIGN KEY (abteilung_id) REFERENCES abteilung(abteilung_id)
    );
´´´

### 3. is-a + Identifying Relationship
sql´´´
    CREATE TABLE mitarbeiter (
        mitarbeiter_id INT PRIMARY KEY,
        name TEXT
    );

    CREATE TABLE fahrer (
        mitarbeiter_id INT PRIMARY KEY,
        fuehrerschein_klasse TEXT,
        FOREIGN KEY (mitarbeiter_id) REFERENCES mitarbeiter(mitarbeiter_id)
    );
´´´

### 4. is-a + Non-Identifying Relationship
sql´´´
    CREATE TABLE person (
        person_id INT PRIMARY KEY,
        name TEXT
    );

    CREATE TABLE kunde (
        kunde_id INT PRIMARY KEY,
        person_id INT,
        status TEXT,
        FOREIGN KEY (person_id) REFERENCES person(person_id)
    );
´´´

---

## DBMS

![Non-Identifying Beziehunngstyp](https://gitlab.com/ch-tbz-it/Stud/m164/-/raw/main/2.Tag/media/Aufbau_DBMS.png)
- **DBS (Datenbanksystem)** ist ein System zur elektronischen Datenverwaltung. Es sollte grosse Datenmengen schnell und effizient speichern können.
- **DBMS (Datenbankmanagmentsystem)** organisiert die Struktur der Daten und kontrolliert alle lesenden und schreibenden Zugriffe auf die Datenbank. Jedes DBMS hat eine Form  und die häutiste ist eine **Rationale Datenbank**.  Zur Abfrage und Verwaltung der Daten bietet ein Datenbanksystem eine Datenbanksprache an, und zwar **SQL**.
- **Datenbank und Datenbasis** sind beides das gleiche. Sie sind die richtigen Speicherplätze. 

### Merkmale DBMS

1. **Integrierte Datenhaltung** -> Einheitliche Verwaltung aller benötigter Daten, Keine Redudanzen, Vielzahl komplexer Beziehungen, Daten verknüpfen
2. **Sprache** -> SQL
    - Datenanfrage (Data Query/Retrieval Language, DQL / DRL → SELECT ),
    - Verwaltung der Datenstruktur (Data Definition Language, DDL → CREATE ),
    - Datenmanipulation (Data Manipulation Language, DML → INSERT ),
    - Berechtigungssteuerung (Data Control Language, DCL → GRANT),
    - Transaktionen (Transaction Control Language, TCL → COMMIT ).
3. **Katalog** -> Katalog (data dictionary) ermöglicht Zugriffe auf die Datenbeschreibungen der Datenbank, die auch als Metadaten bezeichnet werden.
4. **Benutzerzersichten** -> Andere Views des Datenbestands für jeden User
5. **Konsistenzkontrolle** -> Constrains, keine ungewollten Daten in die Datenbank
6. **Datenzugriffskontrolle** -> Rollen
7. **Transaktionen + Merbenutzerfähigkeit** -> Mehrere Einheiten die sich zur Transaktion zusammenfühern, auf einmal aufgeführt werden (Atomarität) und permanent in der Datenbank gespeichert sind (Dauerhaftigkeit). Mehrer Benutzer sollten gleichzeitig daten ablesen und speichern können, ohne das etwas überschrieben wird (isolation). Nach der Transaktion ist die Datenbank in einem gültigen Zustand (Consistency) 
8. **Datensicherung** -> recovery, Verlorene Daten wieder herstellen können anhand eines Backups

### Vorteile des Datenbankeinsatzes

- **Nutzung von Standards**
  - Einheitliche Formate, Namen, Schlüssel, Fachbegriffe
  - Erleichtert Datenorganisation und -integration
- **Effizienter Datenzugriff**
  - Optimierte Speicher- und Zugriffstechniken für große Datenmengen
- **Kürzere Softwareentwicklungszeiten**
  - Wiederverwendbare DBMS-Funktionen
  - Entlastung der Entwickler durch Standardwerkzeuge
- **Hohe Flexibilität**
  - Strukturveränderungen ohne große Auswirkungen (Datenunabhängigkeit)
- **Hohe Verfügbarkeit**
  - Gleichzeitiger Zugriff vieler Nutzer durch Transaktionsverwaltung
  - Änderungen sofort sichtbar nach Transaktionsende
- **Große Wirtschaftlichkeit**
  - Zentralisierte Datenhaltung spart Hardwarekosten
  - Reduktion von Betriebs- und Verwaltungskosten

### Nachteile von Datenbanksystemen

- **Hohe Anfangsinvestitionen**
  - Kosten für leistungsfähige Hardware und DB-Software
- **Weniger effizient für Spezialanwendungen**
  - DBMS ist Allzweck-Software, nicht maßgeschneidert
- **Eingeschränkte Optimierbarkeit**
  - Nur ein Teil der Programme kann ideal bedient werden
- **Mehrkosten für Zusatzfunktionen**
  - z. B. Datensicherheit, Synchronisation, Konsistenzkontrolle
- **Fachpersonal notwendig**
  - Datenbankadministratoren, -entwickler und -designer
- **Zentrale Abhängigkeit**
  - Ausfallrisiko bei zentralem System (Gegenmaßnahme: Verteilung)

### Wichtigste Datenbank-Engines

![Wichtigste Datenbank-Engines](10-wichstigste-db-engines.png)

