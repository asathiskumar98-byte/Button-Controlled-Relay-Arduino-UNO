# ⚡ Button Controlled Relay – Arduino UNO

This project demonstrates how to control an **electrical relay module** using a **push button** and an **Arduino UNO**.  
When the button is pressed, the relay activates; when released, it deactivates — a foundational project for learning **home automation** and **device control**.

---

## 🧠 Overview

A **relay** is an electrically operated switch used to control high-power devices (like lights, fans, or motors) with a low-power signal from a microcontroller.  
This project introduces how to trigger the relay module through a button input signal.

---

## ⚙️ Hardware Requirements

- Arduino UNO  
- 5V Relay Module  
- Push Button  
- 10kΩ pull-down resistor  
- Jumper wires  
- Breadboard  

---

## 🔌 Circuit Connections

| Component | Arduino Pin | Description |
|------------|--------------|-------------|
| Relay Module IN | D8 | Relay control signal |
| Button | D7 | Input signal from button |
| Relay VCC | 5V | Power supply |
| Relay GND | GND | Common ground |
| Button GND | GND | Common ground |

🧩 **Logic:**  
- **Button Pressed (HIGH):** Relay turns **ON**  
- **Button Released (LOW):** Relay turns **OFF**

---

## 💻 Arduino Code

```cpp
const int button = 7;
const int relay = 8;

void setup()
{
  pinMode(relay, OUTPUT);
  pinMode(button, INPUT); 
}

unsigned char button_state;

void loop()
{
  button_state = digitalRead(button);

  if(button_state == HIGH)
  {
    digitalWrite(relay, HIGH);
  }
  else
  {
    digitalWrite(relay, LOW);
  }
}
```
🚀 How It Works
When the button is pressed, the Arduino reads HIGH at pin D7.

This signal activates the relay module through pin D8.

The relay’s switch closes, allowing current to flow to the connected load.

Releasing the button sends a LOW signal, turning the relay OFF.

⚠️ Safety Note
If you’re using the relay to switch AC appliances, always handle wiring with care.
Make sure to isolate low-voltage (Arduino side) and high-voltage (load side) properly.

🧰 Software Tools
Arduino IDE (v2.0 or later)

Arduino UNO Drivers

📸 Output Behavior
Button State	Relay State	Output Device
Pressed (HIGH)	ON	Activated
Released (LOW)	OFF	Deactivated

💡 Applications
Smart Home Automation

Load Control Systems

Motor Control

IoT Energy Management
