# Datenbanksysteme Übersicht

## Inhaltsverzeichnis
1. [MongoDB](#mongodb)
2. [RavenDB](#ravendb)
3. [BaseX](#basex)

## MongoDB
### Grundprinzip der Datenstruktur
- Dokumentenorientierte NoSQL-Datenbank.
- Speichert Daten in BSON-Format (Binary JSON).

### Spezifische Merkmale
- Schema-less: Kein festes Schema erforderlich.
- Skalierbar: Horizontale Skalierung durch Sharding.
- Indexierung: Unterstützung für vielfältige Index-Typen.

### Einsatzbereich (Beispiele)
- Big Data und Datenanalyse.
- Echtzeit-Anwendungen.
- Content-Management-Systeme.

### Vor- und Nachteile
#### Vorteile
- Flexibilität bei der Datenmodellierung.
- Einfache horizontale Skalierung.
- Starke Community und Unterstützung.

#### Nachteile
- Begrenzte Transaktionsfähigkeit.
- Datenintegrität weniger streng als bei relationalen DBen.

### Code-Beispiele
#### Daten einfügen
```javascript
db.collection.insertOne({
  name: "Beispiel Dokument",
  wert: 100
});

```
## RavenDB
### Grundprinzip der Datenstruktur
- Dokumentenorientierte NoSQL-Datenbank, speichert hauptsächlich JSON-Dokumente.

### Spezifische Merkmale
- ACID-Konformität: Zuverlässige Transaktionen.
- Skalierbarkeit: Funktioniert auf Einzelknoten und in Clustern.
- Leistung: Hohe Performance seit Version 4.0.
- Flexibilität in der Datenmodellierung: Einfache Handhabung komplexer Datenstrukturen.

### Einsatzbereiche
- Vielseitig einsetzbar: Ideal für Anwendungen mit komplexen Datenstrukturen.
- IoT und Echtzeit-Anwendungen.

### Vor- und Nachteile
#### Vorteile
- Einfache Datenmodellierung, gute Leistung, Echtzeit-Transaktionen.

#### Nachteile
- Lernkurve für Benutzer von relationalen Datenbanken, spezifisches Know-how erforderlich.

### Daten 
```
{
    "Id": "1",
    "Name": "Max Mustermann",
    "Alter": 35,
    "Beruf": "Softwareentwickler"
},
{
    "Id": "2",
    "Name": "Maria Musterfrau",
    "Alter": 28,
    "Beruf": "Projektmanagerin"
},
{
    "Id": "3",
    "Name": "John Doe",
    "Alter": 40,
    "Beruf": "Systemadministrator"
}
```
### Code-Beispiele

#### Datenabfrage
```ravendb
from Users
where Alter > 30
select Name, Beruf
```

### Antwort
```
[
    { "Name": "Max Mustermann", "Beruf": "Softwareentwickler" },
    { "Name": "John Doe", "Beruf": "Systemadministrator" }
]
```
## BaseX
### Grundprinzip der Datenstruktur
- Speichert XML-Daten effizient in einer festen Struktur.

### Spezifische Merkmale
- Vollständige XQuery-Unterstützung.
- Schnelle Indexierung und Volltextsuche.
- Eingebauter HTTP-Server für RESTful Webdienste.
- Erweiterbar und bietet Versionierungsfunktionen.

### Einsatzbereich (Beispiele)
- Dokumentenverwaltung, CMS.
- Datenintegration, wissenschaftliche Daten.
- Semantic Web-Anwendungen.

### Vor-/Nachteile
#### Vorteile
- Effiziente XML-Datenverwaltung, geringe Ressourcenanforderungen.

#### Nachteile
- Spezialisiert auf XML, Lernkurve für XQuery.

### Code-Beispiele
#### Datenabfrage
```xquery
for $book in //book
return <book>{$book//title}</book>
```