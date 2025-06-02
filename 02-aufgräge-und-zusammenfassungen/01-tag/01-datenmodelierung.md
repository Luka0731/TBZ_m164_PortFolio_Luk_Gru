# Datenmodellierung Grundlagen

## Inhaltsverzeichnis

* [Datenmodellierung](#datenmodellierung)
* [Normalisierung](#normalisierung)

---

## Datenmodellierung

Bei der Datenmodelierung gehte es darum, sich zu überlegen und eine Struktru zu erschaffen, wo und wie Daten gespeichert werden. Man erstellt eine Informationsstrucktur.
Datenmodelierung ist ein Schritt der Datenbankentwicklung. 
In der Datenmodelierung gibt es dann drei aufeinanderfolgende phasen.

### Konseptionelles Datenmodell (ERM)

Das Entity Relationship Model besteht bloss aus Entitäten und Relationen (also z. B. c:1, 1:1). Das ERM ist nicht-implementierungsabhängig, das heisst man muss sich keine gedanken machen, ob es in einem spezifischen DBMS implementierbar ist.
![ERM](https://bildung4u.eu/wp-content/uploads/2020/09/ERM-Lehrer-Schueler-Klasse-1.jpg)

### Logisches Datenmodell (ERD)

Das ERD baut nun auf das ERM auf, jedoch ist es nun implementierungsabhängig. Es enthält nun Attribute mit deren Datentyp, sowhie Fremd- und Privatschlüssel. Die Netzwerkbeziehungen werden mittels Transformationsrtabelle aufgelöst. 
![ERD](https://d2908q01vomqb2.cloudfront.net/b6692ea5df920cad691c20319a6fffd7a4a766b8/2022/06/28/Screenshot-2022-06-24-at-15.38.35.png)

### Physisches Datenmodell

Das Physische Datenmodell ist meistens dann schon der SQL Code (DDL Code davon). Es wird fertig gemacht zum Erstellen der Datenbank und enthält deswegen Aspekte wie Indizes, Partitionierung, Constrains, etc.
![Physisches Datenmodell](https://www.researchgate.net/publication/283105667/figure/fig2/AS:668911880114192@1536492428810/SQL-code-example-of-a-query.png)

---

## Normalisierung

Normalisiertung gehört zur Dantenbakmodellierung. Es gitb fünf aufeinanderfolgende Normalformen, welches nur die ersten drei angeschaut werden. Die Normalformen sind sozusagen "Regeln" zur Datenbankstruktur. Der Sinn ist es damit die Datenintigrität zu verbesser. Wenn man normaliesiert kann man Redudanzen, Anomalien und Inkonsistenzen vermeiden. 
Eine Normalisierung lauft so ab, dass man eine Tabelle mit daten hat. Dann bearbeitet man diese nach jeder Normalform. 

### 1NF

Hier möchte man alle enthaltenen Informationen in seine Atome aufspalten.  Damit ist gemeint z. B. Vorname und Nachname nicht in einem Kästchen stehen zu haben. Dabei muss man Werde auf neuen Kollonen und Zeilen trennen.
![1NF](c:\Users\lukag\Documents\GitHub\TBZ_m164_PortFolio_Luk_Gru\03-resourcen\01-bilder\1nf.jpg)


### 2NF

Aus 1NF + Auftelung in logische Gruppen ergibt 2NF. 
![2NF](c:\Users\lukag\Documents\GitHub\TBZ_m164_PortFolio_Luk_Gru\03-resourcen\01-bilder\2nf.jpg)
Der Theoriesatz den man sich merken kann ist: Alle Nicht-Schlüsselattribute hängen voll funktional vom Primärschlüssel ab (keine Teilabhängigkeiten). Eine Teilabhängigkeit liegt vor, wenn ein Nicht-Schlüsselattribut nur von einem Teil eines zusammengesetzten Primärschlüssels abhängt – nicht vom gesamten Schlüssel.Hier ist ein generiertes Beispiel, was damit gemeint ist:
![Teilabhängigkeit](c:\Users\lukag\Documents\GitHub\TBZ_m164_PortFolio_Luk_Gru\03-resourcen\01-bilder\partielle-abhängigkeit.jpg) 

### 3NF

Aus 2NF * Mehr Aufteilung ergibt 3NF
![3NF](c:\Users\lukag\Documents\GitHub\TBZ_m164_PortFolio_Luk_Gru\03-resourcen\01-bilder\3nf.jpg)
Hier ist der Theoriesatz den man sich merken kann: Befindet sich in der zweiten Normalform und kein Nichtschlüsselattribut ist transitiv von einem Kandidatenschlüssel abhängig. Eine transitive Abhängigkeit liegt vor, wenn ein Nicht-Schlüsselattribut von einem anderen Nicht-Schlüsselattribut abhängt, das selbst vom Primärschlüssel abhängig ist. Ein Beispiel ist:
![Transitive Abhängigkeit](c:\Users\lukag\Documents\GitHub\TBZ_m164_PortFolio_Luk_Gru\03-resourcen\01-bilder\transitive-abhängigkeit.jpg)
