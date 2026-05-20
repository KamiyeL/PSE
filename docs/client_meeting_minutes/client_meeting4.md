# Protokoll – Kundenmeeting  
**Datum:** 21.04.2026  
**Projekt:** Odoo IoT – Digital Signage  
**Kunde:** Abilium GmbH  

---

## 1. Update Projektstand
Wir haben nun einen funktionierenden API Server in unserem Odoo modul. So haben wir im Odoo modul ein fertiges UI womit sich neue Geräte einfach registrieren und verwalten lassen. Des weiteren steht das Grundgerüst des generischen Renderers, den man bereits für einige Module gut nutzen kann. Bei der konfiguration lässt sich nun jedem TRMNL Gerät eine ID hinzufügen, welche als indentifyer auf dem Display angezeigt wird Ausserdem lässt sich einstellen, von welchen Nutzern die Daten für das entsprechende Modul angezeigt werden sollen. Man kann in Dropdownmenues auswählen welches Modul man darstellen will, welcher Layouttype dabei verwendet werden soll, welcher View Mode man will und woher die Daten stammen sollen. 

## 2. Ziele nächste Iteration
### 2.1 Generische Implementierung
Die bestehenden Funktionen müssen noch verbessert werden. Zum Beispiel sollte die Konfiguration einfach möglich sein und wir sollten für die Module sinvolle default Einstellungen setzen. Die Kompatibilität der Odoo Module und den Layouttypes sollte noch geprüft und falls nötig im Konfigurationsmenu gefiltert werden. Allgemein muss der gesammte Code noch refactored und Dokumentiert werden, sowie müssen Testcases mit zugrhöriger Dokumentation erstellt werden. Die Projektstruktur sollte ebenfalls optimiert werden. Fokus liegt auf folgenden Modulen, welche für den Kunden besonders relevant sind: Kalendder, To-Do-Liste, CRM, Point of Sale.

### 2.2 Eigener Server für TRMNL Display
Auch bei diesem Feature sollte der Code noch refactored werden. Einige kleine Funktionen müssen noch implementiert werden: Pingen von TRMNL Geräten sowie einen Reset-Button im UI. Das UI kann noch verschönert werden und die Dokumentation kann noch ausführlicher gestaltet werden. Zu den bestehenden Tests sollte ebenfalls noch eine detaillierte Dokumentation verfasst werden, sowie eine Anleitung für das Setup und Nutzung des Moduls. Die Funktionalität der https Kommunikation sollte in ein separates Odoo Modul ausgelagert werden und optional könne man die Kommunikation mit https implementieren.

## 3. Nächster Termin
Für die Besprechung der 4. Iteration und das Planen der 5. Iteration haben wir einen Termin am 12.05.2026 vereinbart, dann möchten wir ein möglichst fertiges Produkt präsentieren können, damit der Kunde letzte Wünsche anbringen kann.