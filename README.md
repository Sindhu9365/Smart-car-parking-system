# Smart-car-parking-system
This is a smart car parking system built using the ESP32 microcontroller,ultrasonic sensors,servo motor, and an I2C LCD display. It detects the availability of parking slots and automatically opens the gate when a vehicle arrives, provided there is available space.
Features

- Detects vehicles in 2 parking slots using ultrasonic sensors.
- Displays slot status (Free/Occupied) on an LCD display.
- Automatically opens the entry/exit gate using a servo motor.
- Prevents entry when parking is full.
- Real-time status updates via Serial Monitor and LCD.

---

🛠️ Hardware Requirements

- ESP32 board  
- 4 × HC-SR04 Ultrasonic Sensors  
  - 2 for slots  
  - 1 for entry  
  - 1 for exit  
- 1 × Servo Motor (e.g., SG90)  
- 1 × I2C 16x2 LCD Display (Address: `0x27` or `0x3F`)  
- Jumper wires and breadboard  
- External power supply (optional, for servo)

---

⚙️ Pin Connections

| Component       | ESP32 Pin |
|----------------|-----------|
| Servo          | D4        |
| Slot 1 Trig    | D13       |
| Slot 1 Echo    | D12       |
| Slot 2 Trig    | D14       |
| Slot 2 Echo    | D27       |
| Entry Trig     | D26       |
| Entry Echo     | D25       |
| Exit Trig      | D33       |
| Exit Echo      | D32       |
| I2C SDA        | D21 (default) |
| I2C SCL        | D22 (default) |

> 📌 Note: Use 5V to power the ultrasonic sensors and servo. If using a breadboard power supply, ensure it can handle the current draw of the servo.

---

🧪 Software Requirements

- Arduino IDE
- ESP32 board support installed via Board Manager
- Required Libraries:
  - `ESP32Servo`
  - `LiquidCrystal_I2C`
  - `Wire` (usually built-in)

---

 🔧 Installation & Upload

1. Install the required libraries in Arduino IDE.
2. Connect your ESP32 board via USB.
3. Select the correct board and COM port.
4. Upload the provided code.
5. Open Serial Monitor at 115200 baud for debugging.

---

 🖥️ LCD Display Format

- Displays `Free` or `Present` for each slot.
- Shows `FULL` if no slots are available.

---

 🎯 How It Works

- Ultrasonic sensors check for car presence in each slot.
- If a car approaches the **entry sensor**:
  - Gate opens only if a slot is free.
- If a car reaches the **exit sensor**:
  - Gate opens regardless of slot availability.
- LCD and Serial Monitor show real-time statuses.

---

📸 Optional Enhancements

- Add a buzzer for alerts when the lot is full.
- Integrate Wi-Fi to view parking status on a webpage.
- Use an IR sensor for more accurate gate control.
- Add more slots by replicating the sensor setup.

---
 

