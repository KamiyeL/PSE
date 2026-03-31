# Testkonzept V2 — Odoo IoT Digital Signage (TRMNL Integration)

**Projekt:** Odoo IoT Digital Signage (TRMNL Integration)  
**Version:** 2.0  
**Datum:** 31.03.2026

---

## 1. Ziel des Testkonzepts

Ziel dieses Testkonzepts ist die Überprüfung, dass das Odoo-Modul zur Anbindung von TRMNL-Displays funktional korrekt arbeitet und die Kalenderdaten auf dem Display korrekt dargestellt werden.

Im Vergleich zur ersten Version des Testkonzepts wird der Testfokus in V2 stärker auf die tatsächlich relevante Kernfunktionalität gelegt:

- korrekte Bereitstellung der Daten durch Odoo
- korrekte Darstellung der Daten auf dem TRMNL-Display
- korrekte Verarbeitung innerhalb einzelner zentraler Klassen

Dazu werden drei Testarten eingesetzt:

- manuelle Tests
- Golden-Image-Tests
- Unit Tests

---

## 2. Testumfang

Getestet werden die zentralen Funktionen der Lösung:

- Auslesen relevanter Kalenderdaten in Odoo
- Verarbeitung und Formatierung der Daten für die Anzeige
- visuelle Darstellung der Daten auf dem TRMNL-Display
- Verhalten bei Fehlerfälle

---

## 3. Testziele

Mit dem Testkonzept V2 sollen insbesondere folgende Fragen beantwortet werden:

- Werden Kalenderdaten korrekt aus Odoo übernommen?
- Werden Datum, Uhrzeit, Titel und weitere Informationen korrekt formatiert?
- Werden die Daten auf dem TRMNL-Display korrekt dargestellt?
- Bleibt die Darstellung auch nach Änderungen am Code konsistent?
- Funktionieren zentrale Klassen und Methoden isoliert korrekt?
- Reagiert das System bei fehlerhaften oder unvollständigen Eingaben stabil?

---

## 4. Testumgebung

Die Tests werden in der bestehenden Entwicklungsumgebung durchgeführt.

### Komponenten der Testumgebung

- Docker
- Odoo
- PostgreSQL
- lokales Entwicklungssetup der Teammitglieder
- TRMNL-Display bzw. TRMNL-Testumgebung
- HTTP-Testtools wie `curl` oder Postman
- Odoo-Testframework und Python `unittest`

### Testdaten

Für die Tests werden einfache, kontrollierte Testdaten verwendet, zum Beispiel:

- ein Kalendereintrag mit Titel, Datum und Uhrzeit
- mehrere Kalendereinträge zur Prüfung von Reihenfolge und Auswahl
- unvollständige oder fehlerhafte Testdaten für Negativtests

---

## 5. Testarten im Detail

### 5.1 Manuelle Tests

#### Ziel

Überprüfung, dass der End-to-End-Ablauf im realen Nutzungsszenario funktioniert.

#### Vorgehen

- Anlegen eines Kalenderereignisses in Odoo
- Abruf der Daten über den TRMNL-Endpoint
- Anzeige auf dem Display überprüfen
- Änderung eines bestehenden Ereignisses
- erneuter Abruf und Vergleich der Anzeige

#### Prüfkriterien

- korrekte Inhalte
- korrekte Reihenfolge
- korrekte Aktualisierung nach Änderungen
- verständliche und saubere Darstellung
- stabiles Verhalten bei fehlerhaften Eingaben

#### Bewertung

Ein manueller Test gilt als erfolgreich, wenn die Anzeige den erwarteten Inhalten und dem erwarteten Layout entspricht.

### 5.2 Golden-Image-Tests

#### Ziel

Automatisierte Prüfung der visuellen Darstellung.

#### Grundidee

Für ausgewählte Testfälle wird ein erwartetes Referenzbild ("Golden Image") definiert.  
Nach einer Änderung am Code wird die neue Ausgabe erzeugt und mit dem Referenzbild verglichen.

#### Geeignete Prüfaspekte

- Positionierung von Textelementen
- Zeilenumbrüche
- Formatierung von Datum und Uhrzeit
- Darstellung mehrerer Einträge
- Verhalten bei langen Texten
- konsistentes Layout

#### Vorteile

- Änderungen an der Darstellung werden schnell sichtbar
- Regressionen im Layout können früh erkannt werden
- besonders geeignet für Anzeige- und Formatierungslogik

#### Einschränkungen

- Golden-Image-Tests sind empfindlich gegenüber kleinen Layoutänderungen
- Referenzbilder müssen gepflegt werden
- die Testfälle sollten auf wenige, repräsentative Szenarien beschränkt bleiben

#### Auswahl sinnvoller Golden-Image-Testfälle

- Standardfall mit einem Kalendereintrag
- mehrere Einträge
- langer Titel
- fehlende optionale Informationen
- Sonderfall mit leerem Kalender bzw. keiner anzuzeigenden Information

### 5.3 Unit Tests

#### Ziel

Prüfung einzelner Klassen und Methoden unabhängig vom Gesamtsystem.

#### Geeignete Testobjekte

- Formatter-Klassen
- Daten-Mapping zwischen Odoo-Daten und Anzeigeformat
- Validierungslogik
- Hilfsfunktionen zur Auswahl des nächsten Kalendereintrags

#### Beispiele für Unit-Test-Inhalte

- Pflichtfelder werden korrekt geprüft
- Datum/Uhrzeit wird korrekt formatiert
- leere Eingaben werden korrekt behandelt
- ungültige Daten führen zu kontrolliertem Verhalten
- erwartete JSON-Struktur wird korrekt aufgebaut

#### Ziel der Auswahl

Es sollen vor allem solche Klassen getestet werden, die:

- zentrale Logik enthalten
- leicht isolierbar sind
- bei Fehlern direkte Auswirkungen auf die Anzeige haben

---

## 6. Beispiel-Testfälle

### 6.1 Manuelle Testfälle

**TC-M01: Standardanzeige eines Kalendereintrags**  
Ein Kalendereintrag mit Titel, Datum und Uhrzeit wird in Odoo angelegt.  
**Erwartet:** Der Eintrag wird auf dem TRMNL-Display korrekt angezeigt.

**TC-M02: Aktualisierung nach Datenänderung**  
Ein bestehender Kalendereintrag wird geändert.  
**Erwartet:** Nach dem nächsten Abruf wird die aktualisierte Information angezeigt.

**TC-M03: Mehrere Einträge vorhanden**  
Es existieren mehrere Kalendereinträge.  
**Erwartet:** Die Anzeige enthält die erwarteten Einträge in der richtigen Reihenfolge.

**TC-M04: Fehlende oder unvollständige Daten**  
Ein Testdatensatz enthält unvollständige Informationen.  
**Erwartet:** Das System bleibt stabil und zeigt keine unkontrollierten Fehler.

### 6.2 Golden-Image-Testfälle

**TC-G01: Standardlayout mit einem Eintrag**  
Für einen einfachen Kalendereintrag wird ein Referenzbild hinterlegt.  
**Erwartet:** Die generierte Ausgabe stimmt mit dem Golden Image überein.

**TC-G02: Langer Titel**  
Ein Eintrag mit langem Titel wird dargestellt.  
**Erwartet:** Zeilenumbrüche und Layout entsprechen dem Referenzbild.

**TC-G03: Mehrere Einträge**  
Mehrere Einträge werden angezeigt.  
**Erwartet:** Reihenfolge, Abstände und Formatierung stimmen mit dem Referenzbild überein.

**TC-G04: Leere Anzeige / kein relevanter Eintrag**  
Es liegen keine anzuzeigenden Daten vor.  
**Erwartet:** Die leere oder alternative Anzeige entspricht dem Referenzbild.

### 6.3 Unit-Testfälle

**TC-U01: Formatierung von Datum und Uhrzeit**  
Eine Methode zur Ausgabe eines Datums wird getestet.  
**Erwartet:** Das Datum wird im erwarteten Format zurückgegeben.

**TC-U02: Ermittlung des nächsten Kalendereintrags**  
Mehrere Einträge werden an die Logik übergeben.  
**Erwartet:** Der zeitlich nächste relevante Eintrag wird korrekt gewählt.

**TC-U03: JSON-Struktur der Ausgabe**  
Die Datenaufbereitung für den Endpoint wird getestet.  
**Erwartet:** Die Struktur der erzeugten Daten entspricht dem erwarteten Format.

**TC-U04: Behandlung leerer Eingaben**  
Eine Methode erhält leere oder ungültige Eingaben.  
**Erwartet:** Es erfolgt eine kontrollierte Behandlung ohne Absturz.

