# Risk Analysis Week 13
## 1. Refactoring für das manuelle Entfernen von Logs geht schief.
Es sollte noch umgesetzt werden, dass Logeinträge manuell entfernt werden können. Denn aktuell ist es so, dass Liste der Logeinträge unbegrenzt verlängert wird. 
* Eintrittswahrscheinlichkeit: klein
* Gewichtung: Das Entfernen von Logs, wenn ein Problem behoben werden konnte, sorgt für eine übersichtlichere Loghistorie. 
* Gegenmassnahmen: Logik der Logs erneut im Detail anschauen und entsprechend anpassen. 

## 2. Falsche Fehlermeldung bei erstmaliger Registrierung des Geräts kann nicht umgesetzt werden.
* Eintrittswahrscheinlichkeit: mittel
* Gewichtung: Die Fehlermeldung, welche aktuell bei einer erstmaligen Registrierung des Geräts erscheint, ist irreführend. Denn die Fehlermeldung verweist auf die Dokumentation auf der Webseite von TRMNL, welche jedoch für unseren Registrierungsprozess nicht relevant ist. 
* Gegenmassnahmen: Mithilfe der Dokumentation der Fehlercodes einen Weg finden diesen anzupassen.