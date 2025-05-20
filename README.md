# proto2projekt
# Quizspiel mit Node-RED, Display, Tasten und LED-Zeitbalken für Digilab

## Projektbeschreibung

Dieses Projekt ist ein interaktives Quizspiel, das mit Node-RED realisiert wurde.  
- Die **Frage und die Antwortmöglichkeiten** werden auf dem **Node-RED Dashboard** angezeigt (Webbrowser).  
- Die **Antwort wird per Hardware-Tasten** (S5 bis S8) ausgewählt.  
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

## Node-RED Umsetzung

### 1. Dashboard einrichten

- Füge UI Text Nodes hinzu, um die Frage und die 4 Antwortmöglichkeiten anzuzeigen.  
- Beispiel: Frage: „Was ist die Hauptstadt von Deutschland?“  
- Antwortmöglichkeiten als Text anzeigen und mit Tastenbelegung (S5 bis S8) kennzeichnen.

### 2. GPIO Eingänge für Tasten (S5-S8) einrichten

- Nutze die `rpi-gpio in` Nodes, um Tasten-Inputs zu lesen.  
- Konfiguriere die GPIO-Pins, an denen deine Taster angeschlossen sind.  
- Jede Taste sendet eine eindeutige Zahl (1–4) als Payload.

### 3. Antwortauswertung

- Verbinde die GPIO Input Nodes mit einem `function` Node, der die Eingabe mit der richtigen Antwort vergleicht.  
- Beispiel-Code für den Function Node:

```js
const correctAnswer = 2; // z.B. S6 ist die richtige Antwort (Zahl 2)
const pressed = msg.payload;

if (pressed === correctAnswer) {
  return { payload: "richtig" };
} else {
  return { payload: "falsch" };
}
