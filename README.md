/*
  KeyboardAndMouseControl
  Controls the mouse & keyboard for Ardunio Leonardo Pro Micro
  created 3 Sep 2020
  modified 4 Sep 2020
  by Vignesh Kumar B
*/

#include "Keyboard.h"
#include "Mouse.h"

// set pin numbers for the five buttons:
const int Keyboardpin = 6;
const int Ledboardpin = A3;
const int Buzzer = A4;

void setup() { // initialize the buttons' inputs:

  pinMode(Keyboardpin, INPUT);
  pinMode(A3, OUTPUT); //LED 
  
  //Serial.begin(9600);
  //while(!Serial);

  // initialize mouse control:
  //Mouse.begin();
  Keyboard.begin();
}

void loop() {
  if (digitalRead(Keyboardpin) == HIGH) {
        for (int i = 0; i<=20; i++) {
          digitalWrite(A3, HIGH);  delay(120); digitalWrite(A3, LOW);  delay(120); // 5000 sec delay          
        }
        Keyboard.write('@'); Keyboard.write(KEY_BACKSPACE);
        digitalWrite(Keyboardpin, LOW);  delay(20000); //20sec
  }
  digitalWrite(A3, LOW);
  digitalWrite(Keyboardpin, HIGH);    delay(25000);  //25sec
  delay(10000);  // upto 10 seconds delay
}
