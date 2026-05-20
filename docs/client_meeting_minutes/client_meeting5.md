# Protokoll – Kundenmeeting  
**Datum:** 12.05.2026  
**Projekt:** Odoo IoT – Digital Signage  
**Kunde:** Abilium GmbH  

---

## 1. Update Projektstand
Wir haben nun das UI erweitert so dass man ein TRMNL Display Resetten und aus der Datenbank entfernen kann. Zudem kann ein Admin festlegen, welche Richtlinien gelten, um ein neues Display zu registieren. Des weiteren konnte nun ein generischer Renderer implementiert werden. Damit ist es nun möglich eine beliebige Odoo App auf dem Display darzustellen. 

## 2. Überarbeitung zur Finalisierung
### 2.1 Generische Implementierung
In der generischen Implementierung sollte noch implementiert werden, dass man nicht nur die Odoo App auswählt, sondern auch noch das Model genau definieren kann. Denn einige Apps haben mehrere Models, welche individuelle Views haben und diese müssen individuell auf dem Display dargestellt werden können. 

### 2.2 Überarbeitung der UI
Die Funktionalitäten für das Reset und das Remove von Geräten sollten noch mit aufgenommen werden in die Standard Odoo Funktionalitäten, welche über das Zahnradsymbol ausgewählt werden können. Damit soll ermöglicht werden, dass man beispielsweise mehrere Geräte auf einmal aus der Datenbank entfernen kann.

## 2.3 Dokumentation
Zur Dokumentation werden wir ein Video erstellen, welches den gesamten Ablauf von der ersten Registration des Geräts bis zum Konfigurieren und Darstellen einer Odoo App auf dem Display zeigt. Ergänzend wird eine Admin-Handbuch erstellt, indem die entsprechenden Schritte schriftlich festgehalten werden. Zusätzlich wird die bestehende Dokumentation zur Struktur und Architektur noch überarbeitet. 