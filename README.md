# Arduino Keypad & RFID Servo Lock System

## Description
This project implements a secure access control system using Arduino with both keypad and RFID authentication. Users can unlock the system by entering a valid passcode or scanning an authorized RFID card. A servo motor actuates the lock based on successful authentication.

## Features
- Dual authentication (Keypad + RFID)
- Passcode validation
- RFID card detection
- Servo-controlled locking mechanism

## Components
- Arduino (Uno/Nano)
- 4x4 Matrix Keypad
- RFID Module (MFRC522)
- RFID Tags/Cards
- Servo Motor (SG90 or similar)
- Jumper wires
- Breadboard

## Wiring


## Installation
1. Clone the repository
2. Open the `.ino` file in Arduino IDE
3. Install required libraries:
   - Keypad
   - Servo
   - MFRC522
4. Upload to your Arduino

## Usage
- Enter the correct passcode OR scan an authorized RFID card to unlock
- Unauthorized attempts will keep the system locked

## Future Improvements
- Add LCD/OLED display for user feedback
- Implement logging of access attempts
- Add buzzer for alerts


