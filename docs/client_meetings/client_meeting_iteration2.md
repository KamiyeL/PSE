# Protokoll – Kundenmeeting  
**Datum:** 16.03.2026  
**Projekt:** Odoo IoT – Digital Signage  
**Kunde:** Abilium GmbH  

---

## 1. Update Projektstand
Das Aufsetzen und die Nutzung von Odoo (inklusive der dazugehörigen PostgreSQL-Datenbank) via Docker sind uns gelungen. Wir haben ein erstes einfaches Odoo-Modul sowie ein TRMNL-Plugin entwickelt, die es uns ermöglichen, Informationen auf dem TRMNL-Display anzuzeigen. Für die Verbindung verwenden wir Webhooks. Damit haben wir die Ziele der ersten Iteration erreicht.

## 2. Dynamische Datendarstellung auf TRMNL
Das Zusammenspiel zwischen unserem Odoo-Modul und dem TRMNL-Plugin kann grob wie folgt beschrieben werden: Das TRMNL-Plugin definiert mithilfe von Platzhaltern, wie die Daten auf dem TRMNL-Display dargestellt werden sollen. Das Odoo-Modul liefert die konkreten Werte, die in diese Platzhalter eingesetzt werden.  

Abilium wünscht sich einen möglichst dynamischen Ansatz zur Darstellung von Daten auf dem TRMNL-Display. Idealerweise soll die Darstellung direkt in Odoo konfiguriert werden können. Wir werden gezielt nach geeigneten Lösungen hierfür suchen.

## 3. Ziel für zweite Iteration
Ziel der zweiten Iteration ist es, einen Odoo-Kalender auf dem TRMNL-Display darzustellen. Abilium schätzt dies als anspruchsvollere, aber zugleich sehr nützliche Funktion ein.

## 4. Datenmigration
Der Kunde hat uns Zugriff auf sein GitHub-Repository gewährt (https://github.com/Abilium-GmbH/pse_trmnl_odoo_connector) und wünscht, dass wir künftig darin arbeiten. Timur übernimmt die Datenmigration und sendet dem Team die Einladungen zum neuen Repository.

## 5. Lizenz
Für unser Projekt werden wir nach Absprache die MIT-Lizenz verwenden.

## 6. Nächster Termin
Wir haben noch keinen Termin vereinbart. Timur wird sich mit Terminvorschlägen bei der Abilium melden.
