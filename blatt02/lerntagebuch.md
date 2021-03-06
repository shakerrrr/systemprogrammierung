---
title:  'Lerntagebuch zur Bearbeitung von Blatt 02'
author:
- Finn Bechinka (finn.bechinka@fh-bielefeld.de)
- Michel-Andre Witt (michel-andre.witt@fh-bielefeld.de)
- Dennis Edler (dennis.edler@fh-bielefeld.de)
...

# Aufgabe

<!--
Bitte hier die zu lösende Aufgabe kurz in eigenen Worten beschreiben.
-->

## Datentypen:
1. Einen Datentypen byte definieren welchen 8 Bit speichern kann.
2. Drei enmuns mit vorgegebenen Elementen und Werten definieren.

## Funktionen:
Eine Funktion ```TM1637_write_byte(byte wr_data)``` in welcher mit dem im folgendem beschriebendem Algorithmus bits (von wr_data) an die LED-Segmentanteige übertragen wird:
Alle Bits werden eizeln von Rechts nach Links laufend übertragen.

1. Clock-Pin auf LOW setzen : ```digitalWrite(PIN_CLOCK, LOW)```
2. Daten-Pin auf LOW (bit == 0) oder HIGH (bit == 1) setzen : ```digitalWrite(PIN_DATA, [LOW ODER HIGH])```
3. Clock-Pin auf HIGH setzen : ```digitalWrite(PIN_CLOCK, HIGH)```
4. Übertragung abschließen : ```TM1637_ack()```

Nach jedem ```digitalWrite()``` Aufruf: ```delayMicroseconds(DELAY_TIMER)``` aufrufen.

## LED-Demo:
Zum Demonstrieren der LED-Segmenteinzeige-Funktionen unterschiedliche Zahlen ausgeben mit ```TM1637_display_number(float number)```.  
Vor der Arbeit mit der LED-Segmentanzeige einmal ```TM1637_setup()``` aufrufen um die Kommunikation zu initialisieren.

## Make:
Ein makefile für das Programm erstellen.

# Ansatz und Modellierung

<!--
Bitte hier den Lösungsansatz kurz beschreiben:
-   Wie sollte die Aufgabe gelöst werden?
-   Welche Techniken wollten Sie einsetzen?
-   Wie sah Ihre Modellierung aus (UML-Diagramm)?
-   Worauf müssen Sie konkret achten?
-->

## Datentypen:
1. Mit Hilfe eines typedefs aus einem unsigned char byte definieren, da chars 8 Bit groß sind.
2. 3 enums mit den angegebenen Elementen und Werten erstellen.

## Funktionen:
Wie schon im Blatt01 gemacht, der Reihe nach mit einer Maske gucken ob ein Bit gesetzt ist oder nicht und dann dem entsprechent mit der ```digitalWrite()``` die Pins auf HIGH oder LOW setzen.

## LED-Demo:
Hier einfach wie der der Aufgabe beschrieben einmal ```TM1638_setup()``` aufrufen und dann mit ```TM1637_display_number()``` unterschiedliche Zahlen ausgen zwischen welchen mit ```delayMicroseconds``` gewartet wird.

## Make:
Wie in der Vorlesung bzw. den __Regeln für das Praktikum__ beschrieben ein makefile für das Programm erstellen.


# Umsetzung

<!--
Bitte hier die Umsetzung der Lösung kurz beschreiben:
-   Was haben Sie gemacht,
-   an welchem Datum haben sie es gemacht,
-   wie lange hat es gedauert,
-   was war das Ergebnis?
-->

## 24.10.2021
### Datentypen
- Größtenteils Fertig
### Funktionen
- Fertig bis auf die Dokumentation
### LED-Demo
- Geschrieben aber noch nicht auf dem pi ausprobiert
## 25.10.2021
### LED-Demo
- Geht nix, keine Ahnung warum
### Make
- Funktioniert aber wir haben es nicht hinbekommen zuerst die .o Dateien zu erstellen und diese dann zusammenzufügen


# Postmortem

<!--
Bitte blicken Sie auf die Aufgabe, Ihren Lösungsansatz und die Umsetzung
kritisch zurück:
-   Was hat funktioniert, was nicht? Würden Sie noch einmal so vorgehen?
-   Welche Probleme sind bei der Umsetzung Ihres Lösungsansatzes aufgetreten?
-   Wie haben Sie die Probleme letztlich gelöst?
-->

Also es war halt viel Neues auf einmal und damit meinen wir nicht nur neu in dem Sinn, dass wir die Sachen aus der Vorlesung zum ersten Mal umsetzen, sondern auch, dass viele Sachen in den Vorlesungen oder woanders nicht erklärt/angesprochen wurden.

Außerdem haben wir keine Ahnung warum die Ausgabe auf die LED-Anzeige nicht funktioniert und wir haben uns auch ausgiebig mit anderen Gruppen ausgetauscht unter welchen auch Gruppen waren bei welchen es funktioniert hat aber am Ende hatte keiner mehr Ideen warum es nicht funktioniert.