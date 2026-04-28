# Meeting Protokoll — 21.04.2026

**Datum:** 21.04.2026  
**Uhrzeit:** 11:15 - 11:45  
**Ort/Medium:** Vorlesungsraum ExWi  

**Sitzungsleitung:** siehe Bemerkung  
**Protokoll:** siehe Bemerkung

## Teilnehmende
- Sascha Friedli
- Timur Umut Turgul
- Claudio Berger
- Leïla Ayinkamiye

## Bemerkung
Es ist unklar, wer ursprünglich Sitzungsleitung und Protokollführung hatte. Timur hat das Protokoll nachträglich rekonstruiert.

## Traktanden
1. User Interface
2. Generischer Renderer
3. HTTPS-Support
4. Beschlüsse

## 1. User Interface
Das aktuelle User Interface für die Geräteverwaltung befindet sich in einem frühen Stadium; geplante Funktionen — z. B. Setzen der Refresh-Rate sowie Löschen und Zurücksetzen von Geräten — sind noch nicht vollständig implementiert.  
Die Arbeitsgruppe, die den generischen Renderer entwickelt, hat ein eigenes UI zur Konfiguration des Renderers erstellt. 
  
Ziel: Die fehlenden Funktionen der Geräteverwaltung schnellstmöglich fertigstellen, damit die Renderer‑Gruppe ihr UI nach Abschluss integrieren kann.

## 2. Generischer Renderer
Eine erste Iteration des generischen Renderers wurde implementiert. Die Arbeitsgruppe wird an weiteren Verbesserungen arbeiten. Siehe auch das erhaltene [Kundenfeedback](../client_meeting_minutes/client_meeting_iteration4.md#21-generische-implementierung) zur generischen Implementierung.

## 3. HTTPS-Support
Der Kunde wünschte eine möglichst direkte Kommunikation zwischen TRMNL-Display und Odoo. Wir haben einen Ansatz gefunden, HTTPS ohne Einsatz eines Reverse-Proxy zu implementieren. Beim Kundentreffen stellte sich heraus, dass die meisten Endnutzer `odoo.sh` verwenden, welches die Verschlüsselung übernimmt; in diesen Fällen ist unsere eigene HTTPS-Lösung nicht zwingend erforderlich. Der Kunde wünscht optional ein zweites Helfermodul für Endnutzer, die `odoo.sh` nicht verwenden und von unserer Implementierung profitieren würden.

## 4. Beschlüsse
- Sascha und Timur: Verbesserung des User Interface.  
- Leïla und Claudio: Weiterarbeit am generischen Renderer.
