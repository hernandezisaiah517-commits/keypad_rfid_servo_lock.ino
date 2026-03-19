/*
Project: Arduino Keypad & RFID Servo Lock System

Description:
This project implements a dual-authentication access control system using
an RFID module and a push-button/keypad input. When a valid RFID card is
detected or input is triggered, a servo motor actuates to simulate a lock.

Components:
- Arduino Uno/Nano
- MFRC522 RFID Module
- Servo Motor (SG90)
- Push Button (or keypad input)
- Jumper wires

Author: Isaiah Hernandez
*/
#include <SPI.h>
#include <RFID.h>
#include <Servo.h>

// RFID Pins
#define SDA_DIO 9
#define RESET_DIO 8

// Create RFID instance
RFID RC522(SDA_DIO, RESET_DIO);

// Servo setup
Servo lockServo;
const int servoPin = 2;
const int buttonPin = 3;

void setup() {
  Serial.begin(9600);

  SPI.begin();
  RC522.init();

  lockServo.attach(servoPin);

  pinMode(buttonPin, INPUT);
}

void loop() {

  // RFID Detection
  if (RC522.isCard()) {
    RC522.readCardSerial();

    Serial.println("Card detected:");
    for (int i = 0; i < 5; i++) {
      Serial.print(RC522.serNum[i], DEC);
    }
    Serial.println();

    unlock();
  }

  // Button Input (simulating keypad/manual override)
  if (digitalRead(buttonPin) == HIGH) {
    lock();
  }

  delay(500);
}

// Unlock function
void unlock() {
  lockServo.write(0);
  delay(500);
}

// Lock function
void lock() {
  lockServo.write(180);
  delay(500);
}
