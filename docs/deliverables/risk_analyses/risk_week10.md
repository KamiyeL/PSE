# Risikoanalysis Week 10
1. Die Kombination der aktuellen UI für die Verwaltung der Geräte und der UI für das Konfigurieren der Inhalte klappt nicht. 
* Eintrittswahrscheinlichkeit: klein
* Gewichtung: Die Kombination dieser beiden UI's ist zentral, damit Geräte im UI verwaltet werden können (z.B. ein Gerät resetten oder löschen) und gleichzeitig im UI konfiguriert werden kann, welche Inhalte auf dem TRMNL Display angezeigt werden sollen. 
* Gegenmassnahmen: Wir haben darauf geachtet, dass beides kombiniert werden kann durch getrennte Seiten in der Ansicht in Odoo.
2. Die generische Implementierung zur Darstellung von allen Odoo Apps auf dem Display nicht komplett umsetzbar, weil die Darstellung in einigen Fällen schwierig ist sauber zu formatieren, so dass es leserlich wird auf dem Display. 
* Eintrittswahrscheinlichkeit: mittel
* Gewichtung: Eine generische Implementierung wird vom Kunden so fern umsetzbar gewünscht, da dies den Einsatzzweck unsers Moduls steigert. 
* Gegenmassnahmen: Gegebenenfalls für die zentralen Apps für den Kunden spezifische Formatierungen implementieren.