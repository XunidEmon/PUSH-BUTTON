# 🔘 PUSH-BUTTON

The push button is used to manually:
- ✅ Start the robot  
- ✅ Trigger auto-calibration  
- ✅ Switch between multiple modes  

It provides flexible control without needing to reconnect or reprogram the Arduino.

---

## 🚀 Arduino Button Input with Internal Pull-up

This project demonstrates how to use a **push button** with an **Arduino Uno** using the internal pull-up resistor, and how to read its state using `digitalRead()`.

---

## ⚙️ Button Types

### 🔹 Type 1: Active-LOW (Default HIGH)

**Behavior:**
- Button NOT pressed: `HIGH (1)` → pin connected to 5V through pull-up resistor  
- Button pressed: `LOW (0)` → pin shorted to GND  

---

### 🔹 Type 2: Active-HIGH (Default LOW)

**Behavior:**
- Button NOT pressed: `LOW (0)` → pin connected to GND  
- Button pressed: `HIGH (1)` → pin connected to 5V through pull-up resistor  

⚠️ Requires **external pull-down resistor**, as Arduino doesn’t have internal pull-down.

---

## 🧰 Components Used

- Arduino Uno R3  
- Push Button  
- Resistor (for pull-down simulation, not needed for internal pull-up)  
- Jumper Wires  
- Breadboard (for prototyping)  
- Voltmeter (optional, to monitor voltage across button terminals)

---

## 🔌 Circuit Explanation (Active-LOW)

- One leg of the push button is connected to **GND**
- Other leg is connected to **Digital Pin 12**
- `pinMode(12, INPUT_PULLUP);` activates Arduino's **internal pull-up resistor**

**🧠 Note:** This makes the default state **HIGH**, and pressing the button pulls it **LOW**.

---

## 🖥️ Arduino Code

```cpp
void setup() {
  Serial.begin(9600);
  pinMode(12, INPUT_PULLUP);
}

void loop() {
  int x = digitalRead(12);     // Read button state
  Serial.println(x);           // 0 = pressed, 1 = released
  delay(1000);                 // Delay for readability
}
