# P3
#include <Servo.h>            
Servo myServo;               
const int potPin = A0;        
int potValue = 0;             
int angle = 0;                
void setup() { 
myServo.attach(9);          
Serial.begin(9600);         
}
void loop() { 
potValue = analogRead(potPin);            
// Read analog value (0–1023) 
angle = map(potValue, 0, 1023, 0, 180);   // Map analog value to 0–180° 
myServo.write(angle); 
// Print values to Serial Monitor 
Serial.print("Potentiometer: "); 
Serial.print(potValue); 
Serial.print(" -> Servo Angle: "); 
Serial.println(angle); 
delay(15);   
}
