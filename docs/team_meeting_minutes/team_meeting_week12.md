# Meeting Protokoll - 11.05.2026

**Datum:** 11.05.2026  
**Uhrzeit:** 19:00-19:45  
**Ort/Medium:** Telefonisch

**Sitzungsleitung:** Leïla Ayinkamiye  
**Protokoll:** Timur Umut Turgul

## Teilnehmende
- Sascha Friedli
- Timur Umut Turgul
- Leïla Ayinkamiye
- Claudio Berger

## Traktanden
1. Update UI und Endpunkt-Logik
2. Update Renderer
3. Dokumentation
4. HTTPS Helfer-Modul
5. Beschlüsse

## 1. Update UI und Endpunkt-Logik
Der Kunde wünscht die Möglichkeit, verschiedene Displays eindeutig identifizieren zu können. Die Firmware des TRMNL-Displays bietet eine Funktion namens "Identify". Ursprünglich sollte diese Funktion genutzt werden, um die `Friendly ID` der Displays anzuzeigen, was sich jedoch als nicht praktikabel herausgestellt hat. Es werden zwei mögliche Lösungen diskutiert:  
- **Option 1:** Eigene Identify-Funktion implementieren. Der Renderer erzeugt ein spezielles Bild, das die MAC-Adresse des Geräts anzeigt, welches beim nächsten Polling an das Gerät gesendet wird.  
- **Option 2:** Auf eine Identify-Funktion verzichten und stattdessen die MAC-Adresse direkt auf jedem vom Renderer erzeugten Bild anzeigen.  

Die Entscheidung wird in der morgigen Kundensitzung eingeholt.

## 2. Update Renderer
Die Feature-Branch, in der der Renderer entwickelt wurde, liegt mittlerweile deutlich hinter der `main`-Branch. Um das Mergen zu vereinfachen, hat Leïla eine neue Branch von `main` aus erstellt und den Renderer integriert. Diese Branch wird noch heute gepusht, damit der Renderer zeitnah in `main` gemerged werden kann.  

Funktionsweise TRMNL-Display: Nach jedem Display-Call vergleicht das Gerät den übermittelten `Filename` mit dem im Speicher vorhandenen. Nur bei Änderung wird das neue Bild heruntergeladen. Daher sollte der Renderer beim Erzeugen eines neuen Bildes immer einen neuen Dateinamen verwenden (beispielsweise durch integriertem Zeitstempel).

## 3. Dokumentation
Sascha hat eine neue Branch für die Projektdokumentation erstellt und begonnen, die Projektstruktur zu erläutern.

## 4. HTTPS Helfer-Modul
Der Kunde wünscht, dass die bestehende HTTPS-Funktionalität mit eigenen Zertifikaten nicht im Hauptmodul, sondern als separates, optionales Helfer-Modul bereitgestellt wird. Timur hat eine entsprechende Umsetzung erstellt und wird diese heute ins Repository pushen.

## 5. Beschlüsse
- Timur: Hochladen des Helfer-Moduls
- Leila: Hochladen der neuen Renderer-Branch
