# Risk Analysis Week 9
1. Die Implementation der Buttons im UI könnte nicht wie vorgesehen funktionieren, da sich die Logik dahinter nicht implementieren lässt. 
* Eintrittswahrscheinlichkeit: gering
* Gewichtung: Dem Kunden ist es wichtig, dass sich gängige Aktionen, wie das Löschen eine Gerätes oder ein Reset direkt im UI umgesetzt werden können, dafür sind diese Buttons zentral. 
* Gegemassnahme: Bei Problemen nachschlagen, welche Funktionen eventuell bereits von Odoo zur Verfügung gestellt werden und dann diese für unsere eigene Implementation nutzen. 
2. Die Kombination der aktuellen UI für die Verwaltung der Geräte und der UI für das Konfigurieren der Inhalte klappt nicht. 
* Eintrittswahrscheinlichkeit: mittel
* Gewichtung: Die Kombination dieser beiden UI's ist zentral, damit Geräte im UI verwaltet werden können (z.B. ein Gerät resetten oder löschen) und gleichzeitig im UI konfiguriert werden kann, welche Inhalte auf dem TRMNL Display angezeigt werden sollen. 
* Gegenmassnahmen: Pair Coding um Schritt für Schritt gegenseitig überprüfen zu können, dass die beiden UI's sauber kombiniert werden können.