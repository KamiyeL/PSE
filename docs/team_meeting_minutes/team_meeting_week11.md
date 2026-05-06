# Meeting Protokoll - 06.05.2026

**Datum:** 06.05.2026  
**Uhrzeit:** 14:30-15:30
**Ort/Medium:** Besprechung im ExWi

**Sitzungsleitung:** Timur Umut Turgul
**Protokoll:** Sascha Friedli

## Teilnehmende
- Sascha Friedli
- Timur Umut Turgul
- Leïla Ayinkamiye
- Claudio Berger

## Traktanden
1. Update API-Logik
2. Update Rendering
3. Besprechung Merging von API-Logik und Update Rendering
4. Beschlüsse

## 1. Update API-Logik
Code Refactoring durchgeführt um nicht mehr gebrauchte Logik entfernt wurde. Zudem noch die Logik für den Reset-Button angepasst, weil bei einem Reset bisher das Gerät nicht korrekt aus der Datenbank entfernt wurden. 

## 2. Update Rendering
Verwendet separates Fenster für Profile. Dort konfigurieren welcher Inhalt auf dem Display dargestellt werden soll. 

## 3. Besprechung Merging von API-Logik und Update Rendering
Wir müssen die Fenster miteinander kombinieren. Das Profile Fenster aus dem Renderer in das View-File der UI integrieren. 
Es muss ein Weg gefunden werden, dass der Renderer den Filename so anpasst, dass sich dieser ändert, damit bei einem Display-Call die Anzeige angepasst wird. 
Es muss eine Verbindung hergestellt werden, dass in jedem Profile die TRMNL-Displays registiert sind, welche ein bestimmtes Profile anzeigen sollen und für jedes Gerät muss das aktuelle Profile abgespeichert sein. Dafür braucht jedes Profile eine Id. Dann müssen wir einen Weg finden, wie der Renderer seine Resultate sauber über unsere API ans Display übermitteln kann. 

## 4. Beschlüsse
- Timur: Fertigstellen Branch Reset-Funktion und Beginn mit Dokumentation für Geräteaufsetzung
- Leila: Fertigstellen des Renderers
- Claudio: Überarbeitet Tasks für den generischen Renderer
- Sascha: Mergen des Reset-Branch und ausführen der Dokumentation der Projektstruktur. 