Wi-Fi and Bluetooth Jamming Prototype
Overview
This project demonstrates a prototype for jamming Wi-Fi and Bluetooth signals using two NRF24L01 wireless transceiver modules controlled by an ESP32 microcontroller. The circuit is designed to provide a hands-on experience with wireless communication and signal interference.

Components Used
3.7V Lithium Battery

Provides power to the circuit.

TP4056 Lithium Battery Charger Module
Used to charge the lithium battery.

Electrolytic Capacitors (2x)

Capacitors used for filtering and stabilization.

Capacitance: 1 µF

Resistor

Resistance: 3700 Ohms

Red LED

Visual indication of circuit status.

Toggle Switch

Used to control the circuit.
Instance ID: 79dd68c7-732a-478c-9d15-2c6b8f6d3275
NRF24L01 Wireless Transceiver Modules (2x)

Used for wireless communication and jamming.

ESP32-WROOM-32UE Microcontroller

Main controller for the circuit.

Circuit Connections

Below is a summary of the key connections in the circuit:

Power Connections:

Connect the positive terminal of the 3.7V battery to the B+ pin of the TP4056 module.
Connect the negative terminal of the 3.7V battery to the B- pin of the TP4056 module.
ESP32 Connections:

Connect the 3v3 pin of the ESP32 to the + pin of the first electrolytic capacitor.
Connect the GND pin of the ESP32 to the - pin of the first electrolytic capacitor.
Connect the GND pin of the ESP32 to the GND pins of both NRF24L01 modules.
Connect the VCC (3V) pins of both NRF24L01 modules to the 3v3 pin of the ESP32.
NRF24L01 Connections:

Connect the MOSI, MISO, SCK, CSN, and CE pins of both NRF24L01 modules to the corresponding GPIO pins on the ESP32 as defined in the code.
LED and Resistor:

Connect the anode of the LED to a GPIO pin on the ESP32 and the cathode to the resistor, which is then connected to ground.
Toggle Switch:

Connect the toggle switch to a GPIO pin on the ESP32 for control.
Code
The code for the ESP32 is written in Arduino IDE and includes libraries for the NRF24L01 modules. The main functionality includes initializing the modules, handling button debouncing, and switching between jamming modes.


Usage
Assemble the circuit according to the connection diagram.
Upload the code to the ESP32 using the Arduino IDE.
Open the Serial Monitor to view status messages and debug information.
Use the toggle switch to control the jamming functionality.
Important Note
Jamming signals can be illegal in many jurisdictions. Ensure compliance with local laws and regulations regarding radio frequency interference before conducting any tests.
