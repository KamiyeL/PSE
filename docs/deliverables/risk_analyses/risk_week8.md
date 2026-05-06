# Risk Analysis Week 8
1. Die Implementation des API Servers im Odoo Modul spiegelt das exakte Verhalten des Servers von TRMNL nicht wieder.
* Eintrittswahrscheinlichkeit: mittel
* Gewichtung: Der Kunde wünscht, dass das Odoo Modul als API Server genutzt werden kann, um unabhängig vom Server von TRMNL zu sein. Denn dies ermöglicht eine verbessert Distribution der TRNML Displays im Zusammaenspiel mit Odoo an Nutzer.
* Gegenmassnahmen: Testsuite noch erweitern, um gezielt fehlerhaftes Verhalten addressieren zu können.