# Risk Analysis Week 12
## 1. Schwierigkeiten die Konfiguration über Models der Odoo Apps zu definieren.
Der Kunde wünscht, dass man beim Konfigurieren der Profiles individuell die Models auswählen kann, da es für gewisse Apps mehrere Models gibt, welche eine individuelle Ansicht haben.
* Eintrittswahrscheinlichkeit: mittel
* Gewichtung: Das Auswählen der Models ist zentral, damit man generisch definieren kann, welche Inhalt exakt auf dem Display dargestellt werden sollte.
* Gegenmassnahmen: Zuerst für eine einzelne App implementieren und überprüfen ob es klappt. Dann in einem nächsten Schritt generalisieren für alle Apps. 
## 2. Umsetzung der Funktionalität für das Identifizieren des Geräts klappt nicht.
Der Kunde wünscht, dass jedes Gerät identifiziert werden kann, beispielsweise mit einem QR-Code, welcher auf dem Display angezeigt wird. 
* Eintrittswahrscheinlichkeit: mittel-gross
* Gewichtung: Die einfache Identifikation von Geräten ist wichtig, denn falls ein Betrieb mehrere Displays nutzt, muss einfach ersichtlich sein, welches Display welchem Ort (z.B. Sitzungszimmer) zugeordnet ist. 
* Gegenmassnahme: In Pair Programming Schritt für Schritt versuchen den Display-Identifier auf das Gerät zu bringen. 