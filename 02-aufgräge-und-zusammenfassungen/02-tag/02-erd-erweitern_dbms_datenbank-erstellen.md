# ERd Erweitern, DBMS und Datenbanken Erstellen

## Inhaltsverzeichnis

* [Generalisierung / Spezialisierung](generalisierung-/-spezialisierung)
* [Beziehungsarten: Indentifying / Non-Identifying Relationship](#beziehungsarten:-indentifying-/-non-identifying-relationship)
* [DBMS](#dbms)
* [](#)
* [](#)
* [](#)

---

### Generalisierung / Spezialisierung

Auch in Datenbanken gibt es eine Art von Vererbung. Die Generalistische Entity ist die "Parant Class" und die Spezialisierte Entity ist die "Childe Class". Die Verwendung von Generalisierung und Spezialisierung vermeidet Redudanzen und verbessert die Datenstruktur.

sql´´´
CREATE TABLE person (
    person_id INT PRIMARY KEY,
    name VARCHAR(100),
    geburtsdatum DATE
);

CREATE TABLE student (
    person_id INT PRIMARY KEY,
    matrikelnummer VARCHAR(20),
    studiengang VARCHAR(100),
    FOREIGN KEY (person_id) REFERENCES person(person_id)
);

CREATE TABLE dozent (
    person_id INT PRIMARY KEY,
    dozentennummer VARCHAR(20),
    fachgebiet VARCHAR(100),
    FOREIGN KEY (person_id) REFERENCES person(person_id)
);
´´´

### Auftrag dazu

1. BMW Z4 Roadster <- Auto   |   Gemüse <- Gurke
4. ![Teilabhängigkeit](c:\Users\lukag\Documents\GitHub\TBZ_m164_PortFolio_Luk_Gru\ki-antwort-generalisierung-und-spezifizierung.jpg) 

---

## Beziehungsarten: Indentifying / Non-Identifying Relationship



---

## DBMS


