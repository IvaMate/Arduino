#include <Wire.h>
#include <Adafruit_MotorShield.h>
#include "utility/Adafruit_MS_PWMServoDriver.h"
#include <Arduino.h>



Adafruit_MotorShield AFMS = Adafruit_MotorShield(); 
Adafruit_DCMotor *myMotor1 = AFMS.getMotor(1);
Adafruit_DCMotor *myMotor2 = AFMS.getMotor(2);
 int switch1Pin = 2 ;        //pin na koji je switch1 spojen
 int switch2Pin = 3 ;
 int switch3Pin = 4 ;

 int stanje_switcha1 = 0 ;
 int stanje_switcha2 = 0 ;
 int stanje_switcha3 = 0 ;

 int zd_st_sw= 0 ; // zadnje stanje switcha 
 

void setup() {
 
AFMS.begin(1000);
myMotor1->setSpeed(150);
myMotor1->run(FORWARD);
myMotor2->setSpeed(150);
myMotor2->run(FORWARD);

 // DEFINIRANJE PINA SWITCHA 1 KAO ULAZA
 pinMode(switch1Pin ,INPUT);         
 pinMode(switch2Pin ,INPUT);            
 pinMode(switch3Pin ,INPUT);  
 Serial.begin(9600);  //postavlja brzinu prijenosa podataka u bitovima u sekundi         
 


}

void loop() {
  stanje_switcha1 = digitalRead(switch1Pin); // procitaj switchev ulazni pin
  stanje_switcha2 = digitalRead(switch2Pin);
  stanje_switcha3 = digitalRead(switch3Pin);

}
