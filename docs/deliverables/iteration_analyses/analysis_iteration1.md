# Iterationsanalyse – Iteration 1
PSE FS2026 – Odoo IoT für Digital Signage

## 1. Ziel der Iteration

Das Ziel der ersten Iteration war es, eine grundlegende Verbindung zwischen einem TRMNL e-Ink Display und Odoo herzustellen.  
Damit sollte überprüft werden, ob Daten aus Odoo erfolgreich an ein TRMNL-Display übertragen und dort angezeigt werden können.

Die Iteration sollte ausserdem dazu dienen:

- die Entwicklungsumgebung aufzusetzen
- die relevanten Technologien (Odoo, Docker, PostgreSQL, TRMNL) kennenzulernen
- eine erste funktionierende End-to-End Verbindung zu implementieren

Als erste User Story wurde daher definiert:

> Als Benutzer möchte ich eine Nachricht aus Odoo auf einem TRMNL-Display anzeigen können, damit Informationen digital dargestellt werden können.

---

# 2. Analyse der Iteration

## 2.1 War der Inhalt der Stories nach dem Planning Game klar?

Die Story war relativ offen formuliert.  
Das grundlegende Ziel – eine Verbindung zwischen Odoo und dem TRMNL-Display herzustellen – war zwar klar, jedoch war der genaue technische Lösungsweg zu Beginn noch nicht definiert.

Während der Iteration zeigte sich, dass mehrere mögliche Ansätze existieren, beispielsweise:

- ein eigenes TRMNL Plugin mit JSON-Daten
- ein Webhook-basierter Ansatz mit Bildgenerierung

Erst während der Recherche wurde klar, welche Lösung realistisch umsetzbar ist.

---

## 2.2 War der Umfang der Stories zu gross oder zu klein?

Der Umfang der Story war für eine erste Iteration angemessen.

Die Story war bewusst relativ breit formuliert, da zunächst grundlegende technische Fragen geklärt werden mussten.  
Für die erste Iteration war es sinnvoll, sich auf einen **minimal funktionierenden Prototyp** zu konzentrieren.

Die Story konnte erfolgreich umgesetzt werden.

---

## 2.3 War die Aufwandschätzung der Stories realistisch?

Die Aufwandschätzung war teilweise zu optimistisch.

Ein grosser Teil der Arbeit bestand nicht aus der eigentlichen Implementierung, sondern aus:

- Recherche
- Setup der Entwicklungsumgebung
- Verständnis der verwendeten Technologien

Dieser Aufwand wurde zu Beginn unterschätzt.

---

## 2.4 Wurde der Aufwand für neue Technologien realistisch eingeschätzt?

Nein, dieser Aufwand wurde deutlich unterschätzt.

Für viele Teammitglieder waren mehrere Technologien neu:

- Odoo
- Docker
- PostgreSQL
- TRMNL API

Insbesondere das Aufsetzen der Entwicklungsumgebung sowie das Verständnis der Architektur von Odoo benötigten mehr Zeit als erwartet.

---

## 2.5 Wurde das Entwicklungstempo realistisch eingeschätzt?

Das Entwicklungstempo war zu Beginn langsamer als geplant.

Der Hauptgrund dafür war der hohe Aufwand für:

- Einrichtung der Entwicklungsumgebung
- Verständnis der Technologien
- technische Recherche

Nachdem die ersten technischen Hürden überwunden waren, konnte die Implementierung jedoch schneller voranschreiten.

---

## 2.6 Gab es Engpässe?

Ein Engpass entstand vor allem beim **Setup der Entwicklungsumgebung**.

Nicht bei allen Teammitgliedern funktionierte das Setup sofort vollständig.  
Dadurch konnten einige Mitglieder bereits mit der Implementierung beginnen, während andere noch mit technischen Problemen beschäftigt waren.

---

## 2.7 Kann die gruppeninterne Kommunikation verbessert werden?

Ja, die Kommunikation kann verbessert werden.

Die Kommunikation erfolgte hauptsächlich über einen WhatsApp-Gruppenchat.  
Dies führte teilweise zu unübersichtlichen Diskussionen und Missverständnissen bezüglich Aufgabenverteilung oder Arbeitsplanung.

Für die nächste Iteration soll daher:

- die Aufgabenverteilung klarer definiert werden
- der Fortschritt stärker über das GitHub Project Board dokumentiert werden
- regelmässigere Abstimmungen stattfinden

---

## 2.8 War die Arbeitsbelastung aller Teammitglieder ähnlich?

Die Arbeitsbelastung war nicht vollständig gleichmässig verteilt.

Einige Teammitglieder investierten mehr Zeit in das Setup und die Implementierung, während andere noch mit technischen Problemen beschäftigt waren.

Grundsätzlich haben jedoch alle Teammitglieder am Projekt gearbeitet.

Für die nächste Iteration soll die Aufgabenverteilung klarer geplant werden.

---

## 2.9 Gab es Leerläufe oder Wartezeiten aufgrund von Abhängigkeiten?

Teilweise gab es kurze Wartezeiten.

Einige Aufgaben konnten erst begonnen werden, nachdem:

- das Odoo-Setup funktionierte
- die Verbindung zum TRMNL-Display getestet werden konnte

Diese technischen Abhängigkeiten führten teilweise dazu, dass einzelne Tasks erst später bearbeitet werden konnten.

---

Der Zeitaufwand innerhalb der Iteration lässt sich ungefähr wie folgt aufteilen:

### Implementation von Stories
Ein Teil der Zeit wurde für die Entwicklung des Odoo-Moduls sowie die Implementierung der Verbindung zum TRMNL-Display verwendet.

### Implementation von Testfällen
In dieser Iteration wurden noch keine automatisierten Tests implementiert.

### Testen
Das Testen bestand hauptsächlich darin, zu überprüfen, ob Nachrichten korrekt auf dem TRMNL-Display angezeigt werden.

### Einarbeiten in neue Technologien
Ein grosser Teil der Zeit wurde in das Erlernen der Technologien investiert, insbesondere:

- Odoo
- Docker
- TRMNL API

### Systemadministration
Dazu gehörten:

- Einrichtung der Entwicklungsumgebung
- Docker-Konfiguration
- Setup von Odoo und PostgreSQL

Dieser Bereich nahm einen erheblichen Teil des Aufwands ein.

### Projektorganisation
Zeit wurde auch in organisatorische Aufgaben investiert, beispielsweise:

- Erstellung und Pflege des **GitHub Project Boards**
- Planung und Strukturierung der Tasks
- Erstellung eines **Arbeitsplans**

Diese Aufgaben waren wichtig, um die Zusammenarbeit im Team zu strukturieren und den Fortschritt der Iteration zu verfolgen.

### Meetings
Ein weiterer Teil der Zeit wurde für **Meetings innerhalb des Teams sowie mit dem Kunden** investiert.  
Diese dienten dazu, Anforderungen zu klären, den aktuellen Stand zu besprechen und nächste Schritte zu planen.

### Dokumentation und Präsentationen
Zusätzlich wurde Zeit für Projektdokumentation und Präsentationen aufgewendet. Dazu gehörten insbesondere:

- Erstellung des **Testkonzepts (Version 1)**
- Vorbereitung des **Requirements-Vortrags**
- Riskanalyse
- Statusreports
- Protokolle
---

# 4. Erwarteter Aufwand für die nächste Iteration

Für die nächste Iteration wird der grösste Aufwand voraussichtlich in folgenden Bereichen liegen:

- Erweiterung der Funktionalität des Odoo-Moduls
- Darstellung von Kalenderdaten aus Odoo auf dem TRMNL-Display
- Verbesserung der Stabilität der Implementierung
- Einführung von Tests
- Verbesserung des Entwicklungsprozesses im Team

---

# 5. Erkenntnisse aus der Iteration

Die erste Iteration hat mehrere wichtige Erkenntnisse geliefert:

1. Der Aufwand für Setup und Technologieverständnis ist höher als erwartet.
2. Ein funktionierender Prototyp früh im Projekt reduziert technische Risiken.
3. Eine klarere Aufgabenverteilung verbessert die Effizienz im Team.
4. Die Nutzung von GitHub sollte stärker standardisiert werden.

---

# 6. Verbesserungen für die nächste Iteration

Für die nächste Iteration wurden mehrere Verbesserungen definiert:

- Verbesserung der Teamkommunikation
- klarere Aufgabenverteilung
- gemeinsamer Setup-Termin, um sicherzustellen, dass alle Teammitglieder die Entwicklungsumgebung korrekt eingerichtet haben
- kurzer Crashkurs zur Nutzung von GitHub und dem Project Board
- stärkere Berücksichtigung von Tests

---

# 7. Fazit

Die erste Iteration hat eine wichtige Grundlage für das Projekt geschaffen.  
Es konnte erfolgreich eine Verbindung zwischen Odoo und dem TRMNL-Display hergestellt werden.

Trotz einiger Heraodoo/action-90/9usforderungen beim Setup und beim Verständnis der Technologien konnte ein erster funktionierender Prototyp implementiert werden.

Die gewonnenen Erkenntnisse helfen dabei, die nächsten Iterationen effizienter zu planen und umzusetzen.

---


## Ergebnis der ersten Iteration

Am Ende der ersten Iteration konnten folgende Ergebnisse erreicht werden:

- Repository und grundlegende Projektstruktur wurden erstellt
- GitHub Project Board zur Aufgabenverwaltung wurde eingerichtet
- Docker-, PostgreSQL- und Odoo-Umgebung läuft lokal
- README mit Setup-Anleitung wurde erstellt
- Odoo-Modulstruktur wurde vorbereitet
- Verbindung zwischen Odoo und dem TRMNL-Display wurde erfolgreich hergestellt

Damit wurde eine technische Grundlage geschaffen, auf der die Implementierung der nächsten Iterationen aufbauen kann.
