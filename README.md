# task1-electrical-servo-motor

servo motor......
the project explan how to connect servo motor with arduno uno use tinkercad and In reality
1- use tinkercad
insert Urdino uno
insert servo motor
insert resistor
insert potentiometer
insert breadboard small
botao 3
Connecting wires

2-write the code
#include <Servo.h>
#define botao 3
#define redLed 12
#define greenLed 11
#define blueLed 13
#define potPin A0

int pot, grau;
Servo servoMotor;

void setup()
{
  pinMode(botao, INPUT);
  pinMode(redLed, OUTPUT);
  pinMode(greenLed, OUTPUT);
  servoMotor.attach(6);
  
  Serial.begin(9600);
}

void loop()
  
{
  
  pot = analogRead(potPin);
  
  grau = map(pot, 0, 1023, 0, 255);
  servoMotor.write(grau); //escreve posicao em graus
  
  Serial.print("pwm: ");
  Serial.println(grau);
  delay(100);
  
  if(grau < 127)
  {
   
    digitalWrite(redLed, LOW);
    digitalWrite(greenLed, LOW);
    digitalWrite(blueLed, HIGH);
  }
  
  else if(grau > 122 && grau < 200)
  {
    digitalWrite(blueLed, LOW);
    digitalWrite(redLed, LOW);
    digitalWrite(greenLed, HIGH);
  }
  
  else
  {
    digitalWrite(blueLed, LOW);
    digitalWrite(greenLed, LOW);
    digitalWrite(redLed, HIGH);
  }
    
}
3-run the code
------------------------------------------------------
*****servo motor in reality****
1-
insert Urdino uno
insert breadboard small
labtop
insert servo motor
wire connecting arduino to laptop
2-write the code
#include <Servo.h>
int pos=0;
Servo servo1; 

void setup() {
  servo1.attach(9);  
  servo1.write(180); 
}

void loop() {
  for (pos = 0; pos <= 90; pos += 1) { 
      delay(10);                
  }
  for (pos = 90; pos >= 0; pos -= 1) { 
      delay(10);                   
  }
}
3-run the code
Connecting wires
