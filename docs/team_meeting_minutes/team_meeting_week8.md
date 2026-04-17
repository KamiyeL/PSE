# Meeting Protokoll - 17.04.2026

**Datum:** 17.04.2026  
**Uhrzeit:** 12:30 - 13:30  
**Ort/Medium:** Gruppenraum ExWi  

**Sitzungsleitung:** Sascha Friedli  
**Protokoll:** Timur Umut Turgul

## Teilnehmende
- Sascha Friedli
- Timur Umut Turgul
- Claudio Berger

## Entschuldigt
- Leïla Ayinkamiye

## Traktanden
1. Update Timur
2. Update Sascha
3. Update Claudio
4. HTTPS-Support
5. Beschlüsse

## 1. Update Timur
- Die API-Endpunkte sowie die dazugehörige Modellierung des TRMNL-Displays sind implementiert. Die Umsetzung ist derzeit auf unverschlüsselte HTTP-Kommunikation im lokalen Netzwerk beschränkt.
- Tests zur Überprüfung des korrekten Antwortverhaltens der API-Endpunkte wurden implementiert.
- Neue Dev-Tools wurden hinzugefügt: Konfigurationsdateien für ruff und pre-commit sowie ein `Makefile` und `scripts/*` zur Vereinfachung der Container-Erstellung und zur automatischen Installation des trmnl-Moduls. Zudem wurde ein Guide geschrieben, der die Nutzung der `make` Befehle erläutert.
- Das Modell des TRMNL-Displays ist bewusst auf jene Felder und Methoden beschränkt, die für die Endpunkt-Logik erforderlich sind. Für die UI-Implementierung muss das Modell entsprechend erweitert werden.
- Ein UI-Grundgerüst wurde implementiert. Einige geplante Funktionalitäten fehlen noch, das UI ist jedoch ausreichend, um dem Kunden beim nächsten Treffen das Serververhalten zu demonstrieren.

### Feature Branches
Im Repository existieren derzeit drei Feature-Branches, die im Folgenden kurz erläutert werden:
- `feature/trmnl-server`: Enthält den gesamten Code, um Odoo als API-Server für TRMNL-Displays zu nutzen. Dies stellt eine vollständige Überarbeitung der vorherigen Iteration dar und beinhaltet auch die oben genannten Tests sowie die neuen Tools. Der Branch liegt als Pull Request (mit ausführlicher Beschreibung der Änderungen) vor und wartet auf Review und Merge durch die anderen Teammitglieder.
- `feature/trmnl-ui`: Enthält den gesamten Code für das UI-Grundgerüst. Ist funktional, jedoch noch nicht vollständig umgesetzt.
- `feature/tooling`: Enthält die oben erwähnten Tools. Dieser Branch dient der sauberen Trennung von Verantwortlichkeiten (Separation of Concerns). Er wurde bereits in die beiden anderen Feature-Branches gemergt und existiert primär zur Nachvollziehbarkeit der eingeführten Tools.

## 2. Update Sascha
- Nach anfänglichen Fehlermeldungen laufen auch bei ihm nun alle Tests fehlerfrei.
- Die Tests wurden überprüft; die wichtigsten Aspekte sind abgedeckt.
- Für die Implementierung von HTTPS erscheint der Einsatz eines Reverse-Proxy-Servers als sinnvollste Option (vgl. unten).

## 3. Update Claudio
- Es liegt noch keine konkrete Implementierung für den Renderer vor.
- Die Umsetzbarkeit des Renderers gemäss den Vorstellungen des Kunden erscheint fraglich.
- Ein realistischerer Ansatz besteht darin, Odoo-Apps in verschiedene Subklassen zu unterteilen und für jede Subklasse einen Adapter sowie einen Renderer zu implementieren.
- Mit der Erstellung des Foliensatzes für die nächste Präsentation wurde bereits begonnen.

## 4. HTTPS-Support
Für die Implementierung der HTTPS-Kommunikation kommen verschiedene Strategien in Frage, die jeweils Vor- und Nachteile haben. Die gängigste und auch von der Odoo-Dokumentation empfohlene Variante ist der Einsatz eines Reverse-Proxy-Servers. Dies erhöht jedoch die Komplexität des Setups erheblich und setzt voraus, dass der Kunde über eine (kostenpflichtige) öffentliche Domain verfügt.

Timur hat bereits auf einem lokalen Feature-Branch eine Implementierung erarbeitet, die HTTPS-Kommunikation ohne den Einsatz zusätzlicher Server ermöglicht. Diese wurde noch nicht auf GitHub gepusht, da sie sich in einem frühen Stadium befindet und bestehende Tests verletzt. Timur wird diesen Branch dennoch zeitnah veröffentlichen, damit Sascha sich daran beteiligen kann.

## 5. Beschlüsse
- Timur: Pusht seine HTTPS-Implementierung und arbeitet weiter an der Umsetzung.
- Sascha: Analysiert die HTTPS-Implementierung und arbeitet weiter an der Umsetzung.
- Claudio: Beginnt mit der Implementierung des Renderers.
