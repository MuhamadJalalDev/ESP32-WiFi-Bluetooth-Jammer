 Wi-Fi and Bluetooth Jamming Prototype (ESP32 + NRF24L01)
 
⚠️ For Educational & Research Use Only
This project is intended strictly for use in controlled environments by certified security researchers. Signal jamming may be illegal in your country. Always consult your local laws before proceeding.

📡 Overview
This prototype demonstrates signal interference techniques using two NRF24L01+ transceivers controlled by an ESP32-WROOM-32UE microcontroller. It cycles through different jamming modes (Wi-Fi, Bluetooth, RC drones) and is intended for learning about wireless protocols, RF behavior, and interference mechanisms in the 2.4 GHz band.

🧰 Components Used
Component	Quantity	Purpose
ESP32-WROOM-32UE	1	Main microcontroller
NRF24L01+ Modules	2	Wireless transceivers for interference
3.7V Lithium Battery	1	Power source
TP4056 Charging Module	1	Lithium battery charging
Electrolytic Capacitors (1µF)	2	Power line stabilization
3700Ω Resistor	1	Current limiting for LED
Red LED	1	Visual status indication
Toggle Switch	1	Manual control of modes





⚙️ Circuit Connections
🔌 Power System
Battery ➜ TP4056 Module:

B+: Connect to battery positive

B-: Connect to battery negative

TP4056 ➜ ESP32 & Peripherals:

OUT+: To ESP32 3V3 pin and NRF24L01 VCC

OUT-: Common ground for all components

Capacitor 1 (Decoupling):

+: To ESP32 3V3

-: To ESP32 GND

🖥️ ESP32 to NRF24L01 Connections
Each NRF24L01+ uses SPI. Use separate CE/CSN pins as defined in the code:

Module 1 (Wi-Fi Jammer)
NRF24L01 Pin	ESP32 GPIO
CE	22
CSN	21
MOSI	23
MISO	19
SCK	18

Module 2 (Bluetooth Jammer)
NRF24L01 Pin	ESP32 GPIO
CE	16
CSN	15
MOSI, MISO, SCK	Same as Module 1 (shared SPI bus)




⚠️ You may need a low ESR capacitor (10µF+) close to each NRF module for stability.

💡 Status LED & Controls
LED:

Anode ➜ ESP32 GPIO (your choice)

Cathode ➜ 3700Ω Resistor ➜ GND

Toggle Switch:

Connected to a digital GPIO pin (used for changing modes)

Boot Button (GPIO 0):

Used to cycle through modes:

IDLE → Wi-Fi Jamming → Bluetooth Jamming → RC Drone Jamming




💻 Software
Language:
Arduino C++ (written for the Arduino IDE)

Libraries Required:
RF24

SPI (built-in)

Main Features:
Initializes both NRF24L01 modules for different modulation types

Sends continuous dummy RF payloads to simulate interference

Allows real-time switching between modes using GPIO input

Displays debug information over Serial Monitor (115200 baud)





🚀 How to Use
Assemble the circuit as per the connections above.

Upload the code to the ESP32 using Arduino IDE.

Power the circuit using a 3.7V lithium battery (fully charged).

Open Serial Monitor (baud: 115200) to view logs.

Use the boot button to cycle between jamming modes.

Observe LED for basic status feedback (optional enhancement).




⚠️ Legal Disclaimer
This code and hardware are provided strictly for educational, experimental, and lawful cybersecurity research purposes.

Signal jamming is illegal in many jurisdictions under telecom laws (e.g., FCC Part 15 in the U.S.). Unauthorized use may lead to severe penalties. Always:
Work in RF-isolated labs
Never transmit outside controlled environments
Get proper regulatory approvals






📎 License
MIT License (if you want to share the source openly).
Please credit original authors or contributors if republished or remixed.




[![Watch the demo](https://github.com/MuhamadJalalDev/ESP32-WiFi-Bluetooth-Jammer/blob/main/uploads/yt.png)](https://youtube.com/shorts/59uEX_QqCXA)



