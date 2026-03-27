# Meeting Protokoll - 27.03.2026

**Datum:** 27.03.2026  
**Uhrzeit:** 12:00 - 13:00  
**Ort/Medium:** ExWi, Gruppenraum 01  

**Sitzungsleitung:** Claudio Berger  
**Protokoll:** Timur Umut Turgul 

## Teilnehmende
- Sascha Friedli
- Timur Umut Turgul
- Claudio Berger

## Entschuldigt
- Leïla Ayinkamiye

## Traktanden
1. Allgemeines  
2. Verbesserte Kalenderdarstellung  
3. Tests  
4. Zweites Feature: Darstellung eines Support-Ticket-Systems  
5. Demo 1 (Sasha & Timur)  
6. Bugfixes  

## 1. Allgemeines
Die Ziele der zweiten Iteration sind grösstenteils erreicht. Unser Modul bietet nun eine Struktur, die modular erweiterbar ist. Daher möchten wir parallel an folgenden Punkten weiterarbeiten:
- Verbesserte Kalenderdarstellung  
- Tests  
- Zweites Feature: Darstellung eines Support-Ticket-Systems

## 2. Verbesserte Kalenderdarstellung
Momentan werden die Kalenderinformationen in einfacher Textform auf dem TRMNL-Display angezeigt. Ziel ist es, diese Informationen ästhetischer darzustellen. Hierfür existiert bereits ein Branch, an dem Leïla arbeitet. Der aktuelle Stand muss noch abgeklärt werden.  
**Update (27.03.2026, 20:18):** Der Branch/PR ist bereit, geprüft und gemergt zu werden.  

## 3. Tests
Neben den üblichen Unit-Tests möchten wir das „Golden Image“-Prinzip einsetzen, um die Korrektheit der Bildgenerierung automatisiert zu prüfen. Claudio wird versuchen dies umzusetzen.

## 4. Zweites Feature: Darstellung eines Support-Ticket-Systems
Der Kunde hatte in früheren Meetings den Wunsch geäussert, eingehende Support-Tickets ebenfalls auf dem TRMNL-Display anzeigen zu können. Dieses Feature soll als zweites implementiert werden. Da es nicht zu den vereinbarten Zielen der zweiten Iteration gehört, wird keine konkrete Zuweisung vorgenommen. Teammitglieder können sich diesem Feature widmen, wenn sie Kapazitäten haben.  

## 5. Demo 1 (Sasha & Timur)
1. Sasha übernimmt die Begrüssung und die Projektvorstellung.  
2. Timur demonstriert anschliessend das Setup des TRMNL-Displays und der Entwicklungsumgebung.  
3. Zum Abschluss zeigt Sasha Odoo und unser Modul.  

Sasha und Timur treffen sich am Montag, 30.03., um 10:00 Uhr, um die Demo erneut zu besprechen.  

## 6. Bugfixes
- Beim Klick auf den Button „Modul Info“ in unserem Modul wird ein Fehler ausgegeben.  
- Im README.md beginnt der Befehl zur Datenbankinitialisierung fälschlicherweise mit „podman“ anstatt „docker“.  

Timur wird die Bugfixes übernehmen.
