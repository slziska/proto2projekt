# proto2projekt
# Quizspiel mit Node-RED, Display, Tasten und LED-Zeitbalken für Digilab

## Projektbeschreibung

Dieses Projekt ist ein interaktives Quizspiel, das mit Node-RED realisiert wurde.  
- Die **Frage und die Antwortmöglichkeiten** werden auf dem **Node-RED Dashboard** angezeigt.  
- Die **Antwort wird per Hardware-Tasten** ausgewählt.  
- Nach der Antwort zeigt ein externes **LCD-Display** an, ob die Antwort „richtig“ oder „falsch“ war, oder ob die Zeit abgelaufen ist („Time Out“).  
- Gleichzeitig simuliert ein **LED-Zeitbalken** eine Zeitbegrenzung, indem vier LEDs nacheinander aufleuchten. Wird keine Antwort innerhalb der Zeit gegeben, endet das Spiel mit „Time Out“.

---

## Voraussetzungen

- Raspberry Pi mit installiertem Node-RED  
- Node-RED Dashboard installiert (`node-red-dashboard`)  
- Externes LCD-Display (z.B. I2C LCD 16x2)  
- 4 Taster (S5 bis S8) als digitale Inputs  
- 4 LEDs als Zeitbalken  
- Verkabelung gemäß Hardware-Anleitung (siehe unten)  
- Python 3 auf Raspberry Pi (für Display- und LED-Steuerung)  
- Bibliotheken: `RPi.GPIO` und `smbus2` oder `lcd`-Bibliothek für das Display
  
---

## Umsetzung

In der Schule gab es öfters Probleme mit dem raspberry pi, deswegen hatte ich die meiste Arbeit zuhause erledigt.
Ich habe fast alles nach Planung umsetzen können, ausser des LCDs, dafür habe ich ein paar extra Knöpfe hinzugefügt.
Ich hatte die grössten Probleme beim LCD und beim zurücksetzen des Timers + LEDs, habe am Schluss mit Hilfe von Mitschüler eines der Probleme lösen können.
Nach der Umsetzung der Planung habe ich den "erneut Versuchen" Button hinzugefügt um es zu vereinfachen.

---

## Digilab

Vom Digilab war geplannt 4 Tasten, 4 LEDs und die LCD einzuarbeiten, am Ende wurden es 4 Tasten, 8 LEDs und leider kein LCD durch ein unbekanntes Problem.
Da ich auch Probleme hatte mit der zurücksetzung der LEDs, fiehl mir am Ende die Zeit um noch das Problem des LCDs zu beheben, weswegen ich es ein wenig umgeplant hatte.

---

## Verantwortung

Die Idee und den Grundsatz des Flows habe ich von selber gemacht, für Funktionen hatte ich mir ein wenig extra Hilfe holen müssen.
Abgesehen von den Problembereichen habe ichb den Rest selbstständig mit Hilfe des Internets gemacht, aber ich habe darauf aufgepasst, dass ich auch alles verstehe, um Probleme schneller lösen zu können.
