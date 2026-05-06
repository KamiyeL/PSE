# Risk Analysis Week 6
1. Verbindung in TRMNL mit eigenem Server ist nicht umsetzbar.
* Eintrittswahrscheinlichkeit: klein
* Gewichtung: Die Umsetzung über einen eignen Server hat für den Kunden hohe Priorität, da dies das Einrichten der Geräte für Unternehmen deutlich erleichtert. Denn das Einrichten über den TRMNL Server ist aufwändig und eventuell aus Datenschutzgründen problematisch.
* Gegenmassnahmen: Einlesen in Dokumentation von TRMNL zur Nutzung eigener Server.
2. Umsetzung der Kommunikation von TRMNL Display mit Odoo direkt nicht umsetzbar, da Logik von TRMNL Server nicht Open Source.
* Eintrittwahrscheinlichkeit: mittel
* Gewichtung: Die Implementation der Kommunikationslogik direkt in Odoo würde die Komplexität der Verbindung zwischen Display und Odoo reduzieren. 
* Gegenmassnahmen: Zugang zu Sourcode suchen und abklären ob dieser umgeschrieben werden kann für eine Implementation in Odoo.
3. Die Darstellung durch generischer Renderer auf Basis des Views von Odoo auf dem TRMNL Display ist nicht lesbar.
* Eintrittswahrscheinlichkeit: hoch
* Gewichtung: Für den Kunden wäre es zentral, dass generisch eine beliebige Auswahl von Apps aus Odoo auf dem TRMNL Display dargestellt werden können. 
* Gegenmassnahme: Sourcode des Odoo View verstehen und in Pair Coding nach Implementationsmöglichkeit in Odoo suchen.