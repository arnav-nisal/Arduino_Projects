# Arduino Projects: Bluetooth Door Lock & Automatic Dustbin

This repository contains the Arduino source code for a couple of my early hardware projects. These were explorations into microcontroller programming, sensor integration, and real-world automation.

## Repository Status

**Please Note:** This is a public archive and is **not actively maintained**. The code is preserved here for historical and personal reference and does not reflect my current skill level.

The hardware, schematics, and mobile app code associated with these projects are not included. The code is provided as-is and may require modification to work with modern libraries or different hardware components.

---

## Project 1: Bluetooth Solenoid Door Lock

This is the primary project in this repository. It's an Arduino-based system designed to control a solenoid door lock using a smartphone's fingerprint sensor for authentication.

### Overview

The goal was to create a secure, keyless entry system. Instead of building a dedicated fingerprint scanner, this project leverages the existing, secure sensor on a smartphone. The phone handles the biometric authentication and then sends a secret command to the Arduino via Bluetooth.

### How It Works

1.  **Authentication (on Phone):** A companion mobile application (not included in this repo) is used. The user authenticates with their registered fingerprint on the phone.
2.  **Transmission:** Upon successful authentication, the phone app sends a pre-defined **secret phrase** or command to the Arduino via a Bluetooth connection.
3.  **Validation (on Arduino):** The Arduino, equipped with a BT-05 Bluetooth module, constantly listens for incoming data. It compares the received data to the hard-coded secret phrase.
4.  **Unlock:** If the received data **matches** the secret phrase, the Arduino sends a signal (e.g., a HIGH pulse) to a relay or transistor, which in turn powers the **solenoid door lock**, causing it to unlock.

### Key Hardware

* **Arduino Uno / Nano:** The microcontroller processing the logic.
* **BT-05 Bluetooth Module:** To establish a serial communication link with the smartphone.
* **Solenoid Door Lock:** The electric lock mechanism.
* **Relay Module / Transistor:** To safely control the high-current solenoid with the Arduino's low-current GPIO pin.
* **Smartphone:** (Running a custom app) To act as the authentication terminal.

---

## Project 2: Automatic Dustbin

The code for an automatic, touchless dustbin is also included in this repository.

### Overview

This project uses an ultrasonic sensor to detect when a hand or object is waved above the dustbin. When triggered, it activates a servo motor to automatically open the lid.

This code is included here simply because it was being developed during the same period as the door lock project.

### Key Hardware

* **Arduino Uno / Nano**
* **HC-SR04 Ultrasonic Sensor:** To detect proximity.
* **Servo Motor (e.g., MG90S or SG90):** To actuate the lid.
