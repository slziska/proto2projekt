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

