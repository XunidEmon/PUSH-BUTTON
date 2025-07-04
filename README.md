# PUSH-BUTTON
# Arduino Button Input with Internal Pull-up

This project demonstrates how to use a **push button** with an **Arduino Uno** using the internal pull-up resistor, and how to read its state using `digitalRead()`.

## 🧰 Components Used

- Arduino Uno R3
- Push Button
- 10kΩ Resistor (used for simulation, but not needed in real pull-up)
- Jumper Wires
- Breadboard (if in physical setup)
- Voltmeter (to measure voltage across button terminals)

## 🔌 Circuit Explanation

- One leg of the push button is connected to **GND**.
- The other leg is connected to **Digital Pin 12**.
- `pinMode(12, INPUT_PULLUP);` enables Arduino's **internal pull-up resistor**, so no external pull-up is needed.
- When the button is **not pressed**, Pin 12 reads **HIGH (1)** due to pull-up.
- When the button is **pressed**, Pin 12 is connected to **GND**, so it reads **LOW (0)**.

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
