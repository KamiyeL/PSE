# Meeting Protokoll - 15.05.2026

**Datum:** 15.05.2026  
**Uhrzeit:** 18:30-19:15  
**Ort/Medium:** Telefonisch

**Sitzungsleitung:** Sascha Friedli  
**Protokoll:** Timur Umut Turgul

## Teilnehmende
- Sascha Friedli
- Timur Umut Turgul
- Leïla Ayinkamiye
- Claudio Berger

## Traktanden
1. Fehlercodes  
2. `Friendly ID`  
3. Dokumentation  
4. Tutorial-Video  
5. Renderer  
6. Weitere PRs  
7. Fehlerlogs  
8. Beschlüsse 

## 1. Fehlercodes
Wenn ein TRMNL-Gerät, das entweder unbekannt ist oder ein ungültiges API-Token verwendet, eine Anfrage an `/api/display` stellt, antwortet der Server mit einem semantisch korrekten Fehlercode. Dieser führt dazu, dass eine in der Firmware hinterlegte Fehlermeldung auf dem Gerät angezeigt wird. Diese Meldung weist den Nutzer darauf hin, die Geräteregistrierung auf trmnl.com abzuschliessen.

Diese Meldung ist jedoch irreführend, da der Benutzer keine Aktionen auf trmnl.com durchführen muss, um unseren Server zu verwenden.

## 2. `Friendly ID`
Der Server generiert für jedes Gerät, das über `/api/setup` oder `/api/display` registriert wird, eine `Friendly ID` und speichert diese im entsprechenden Geräteeintrag. Geräte, die über `/api/display` hinzugefügt werden, besitzen bereits eine `Friendly ID`; dennoch wird serverseitig eine neue ID generiert und gespeichert.

Dies führt zu einer Inkonsistenz zwischen der im Server gespeicherten ID und der tatsächlich im Gerät hinterlegten ID. Da es keine Möglichkeit gibt, die auf dem Gerät gespeicherte `Friendly ID` auszulesen, beschliessen wir, die `Friendly ID` aus dem Code zu entfernen, da sie nicht zwingend erforderlich ist und unnötige Komplexität verursacht.

## 3. Dokumentation
Es wird beschlossen, ein Benutzerhandbuch zu erstellen. Am Renderer wird derzeit noch gearbeitet, jedoch sind im restlichen Code keine grösseren Änderungen mehr zu erwarten. Daher kann bereits mit der Dokumentation der Einrichtung des TRMNL-Displays sowie der Verbindung zum Server begonnen werden.

## 4. Tutorial-Video
Der Kunde hat in der letzten Sitzung den Wunsch nach einem instruktiven Tutorial-Video für Endnutzer geäussert. Dieses Vorhaben soll umgesetzt werden.

## 5. Renderer
Leïla hat eine Pull Request für den Renderer erstellt, die bereits von Timur überprüft wurde. Es bestehen noch einige offene Punkte, die vor dem Mergen geklärt werden müssen. Leïla wird den Renderer weiterentwickeln und anschliessend ein erneutes Review anfordern.

## 6. Weitere PRs
Timur hat zwei Pull Requests erstellt:

- `fix(trmnl): remove identify function and refactor`: Entfernung der `identify`-Funktion sowie kleinere Aufräumarbeiten.  
- `refactor(trmnl): rework device models and views`: Anpassungen der Refresh-Rate sowie UI-Updates.

## 7. Fehlerlogs
- Aktuell besteht keine Möglichkeit, von TRMNL-Geräten erzeugte Fehlerlogs zu löschen. Es wird beschlossen, diese Funktion als UI-Option zu implementieren.  
- TRMNL-Geräte erzeugen bei der Erstregistrierung über `/api/setup` einen noch nicht eindeutig identifizierten Fehler, der zu einem Fehlerlog führt.

## 8. Beschlüsse
- Claudio: Beginnt mit der Umsetzung des Video-Tutorials und bereitet Demo 2 vor.  
- Timur: Überarbeitet die Fehlercodes, entfernt die `Friendly ID`, implementiert die Löschfunktion für Fehlerlogs und behebt den Fehler bei der Erstregistrierung.  
- Sascha: Reviewt `fix(trmnl): remove identify function and refactor` sowie `refactor(trmnl): rework device models and views` und beginnt mit der Erstellung des Benutzerhandbuchs.  
- Leïla: Arbeitet weiter am Renderer-Code und bereitet ebenfalls Demo 2 vor.
