# Jingyu_CCA_Mechatronics_2020
homework

# week 1
![week1](/image/Week_1_01.png)
# week 2
![week2](/image/Week_2_04.gif)
![week2](/image/Week_2_05.gif)
# week 3
![week3](/image/IMG_1525_4.gif)
# week 4
![week4](/image/led1.gif)
```cpp
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(12, OUTPUT);
  pinMode(13, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(12, HIGH);   
  delay(1000);
  digitalWrite(12, LOW);   
  digitalWrite(13, HIGH);    
  delay(1000);
  digitalWrite(13, LOW);   
  digitalWrite(12, HIGH);   
  delay(100);
  digitalWrite(12, LOW);
  digitalWrite(13, HIGH);    
  delay(100);
  digitalWrite(13, LOW); 
  digitalWrite(12, HIGH);   
  delay(100);
  digitalWrite(12, LOW); 
  digitalWrite(13, HIGH);    
  delay(100);
  digitalWrite(13, LOW);
       
}
```
![week4](/image/led2.gif)
```cpp 
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(12, OUTPUT);
  pinMode(13, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(12, HIGH);   
  delay(1000);
  digitalWrite(12, LOW);    
  digitalWrite(13, HIGH);    
  delay(1000);
  digitalWrite(13, LOW);   
       
}
```
# week 5
![week5](/image/sensor_led.gif)
```cpp
int outputValue=0;
void setup() {
  // put your setup code here, to run once:
 Serial.begin(9600);
 pinMode(A0,INPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
 int sensorValue = analogRead(A0);
 Serial.print("sensorValue; ");
 Serial.print(sensorValue);
 delay(1);

 outputValue = constrain(sensorValue, 30, 80);
 outputValue = map(outputValue, 30, 80, 255, 0);
 analogWrite(9, outputValue);
 delay(100);

outputValue = constrain(sensorValue, 30, 80);
 outputValue = map(outputValue, 30, 80, 255, 0);
 analogWrite(10, outputValue);
 delay(100);

 outputValue = constrain(sensorValue, 30, 80);
 outputValue = map(outputValue, 30, 80, 255, 0);
 analogWrite(11, outputValue);
delay(100);

  outputValue = constrain(sensorValue, 30, 80);
 outputValue = map(outputValue, 30, 80, 255, 0);
 analogWrite(12, outputValue);
 
 Serial.print("\t outputValue; ");
 Serial.println(outputValue);
 delay(1);
}
```
![week5](/image/sensor_led2.gif)
```cpp
int outputValue=0;
void setup() {
  // put your setup code here, to run once:
 Serial.begin(9600);
 pinMode(A0,INPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
 int sensorValue = analogRead(A0);
 Serial.print("sensorValue; ");
 Serial.print(sensorValue);
 delay(1);

 outputValue = constrain(sensorValue, 30, 50);
 outputValue = map(outputValue, 30, 50, 255, 0);
 analogWrite(9, outputValue);
delay(100);

outputValue = constrain(sensorValue, 50, 100);
 outputValue = map(outputValue, 50, 100, 255, 0);
 analogWrite(10, outputValue);
 delay(100);

 outputValue = constrain(sensorValue, 100, 150);
 outputValue = map(outputValue, 100, 150, 255, 0);
 analogWrite(11, outputValue);
delay(100);

  outputValue = constrain(sensorValue, 150, 200);
 outputValue = map(outputValue, 150, 200, 255, 0);
 analogWrite(12, outputValue);
 
 Serial.print("\t outputValue; ");
 Serial.println(outputValue);
 delay(1);
}
```

# week 6
![week6](/image/sensor_motor2.gif)
```cpp
int outputValue=0;
void setup() {
  // put your setup code here, to run once:
 Serial.begin(9600);
 pinMode(A0,INPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
 int sensorValue = analogRead(A0);
 Serial.print("sensorValue; ");
 Serial.print(sensorValue);


 outputValue = constrain(sensorValue, 900, 1000);
 outputValue = map(outputValue, 1000, 900, 500, 0);
 analogWrite(9, outputValue);


Serial.print("\t outputValue; ");
 Serial.println(outputValue);
 delay(1);
}
```

# week 10 Midterm Project
- image of first version  
I tried to use gears to connect the dragon dance machine and the motor.  
The motor can not provide enough power to drive the dragon dance machine in this version.  
![week10](/image/IMG_1683.jpg)

- image of second version  
I used bluetape toconnect motor and dragon dance machine.  
I test it with battries.  
![week10](/image/test1.gif)

- image of third version  
Connect dragon dance machine with UNO board.  
![week10](/image/test2.gif)

- [Midterm Project](https://www.youtube.com/watch?v=KcEAxE8rQ0Y)

# week 11
- Sketch for final project  
![week11](/final//Week1/IMG_0242.PNG)
At beginning, I want to keep the photoresistor to sense the brightness of light and then start or stop the dragon dance machine. But this is almost the same as what I did for midterm project. I want to have something new for the final.  
![week11](/final//Week1/IMG_0241.PNG)
So I plan to use IR remote control to start it and then change the speed of it according to the distance between it and people who using it.  

- Try to control a led light with IR remote control
![week11](/final//Week2/IMG_1791.jpeg)

![week11](/final//Week2/IMG_1792.jpeg)

I tried to control LED light with remote control. But it doesn't work so well. The remote control can not work stably, and that cause a lot of problem for further development.  
- Code 1  
```cpp
#include <IRremote.h>
const int RECV_PIN = 4;
const int redPin = 8;

int togglestate = 0;  // this toggle state never gets changed so it will always be 0

unsigned long key_value = 0;

IRrecv irrecv(RECV_PIN);
decode_results results;

void setup() {
  irrecv.enableIRIn();
  pinMode(redPin, OUTPUT);
  
}
void loop(){

  // This code will print out the values received from the remote controller.
  // you can use this to determine what codes are sent by each remote control button
  
    if (irrecv.decode(&results)){
        Serial.println(results.value, HEX);
        irrecv.resume();
    }

  
    // code taken from https://www.circuitbasics.com/arduino-ir-remote-receiver-tutorial/
    if (irrecv.decode(&results)){
 
        if (results.value == 0XFFFFFFFF)
          results.value = key_value;

        switch(results.value){
          case 0xFFA25D:
          Serial.println("Jingyu button 1");
          // add other functions here to execute when this button is pushed
          // such as:
              digitalWrite(redPin, HIGH);
          break;
          case 0xFF30CF:
          Serial.println("Jingyu button 2");
          // add other functions here to execute when this button is pushed
              digitalWrite(redPin, LOW);
          break;
          case 0xFF18E7:
          Serial.println("Jingyu button 3");
          // add other functions here to execute when this button is pushed
          break;
          case 0xFFFFFFF:
          Serial.println("nothing?");
          break;
        }
        key_value = results.value;
        irrecv.resume(); 
    }
    
//  // develop this code later - once you've figured out what code your remote is sending  
//  if (irrecv.decode(&results)){
//    
//    switch(results.value){
//      case 0xFFA250:
//      if (togglestate==0){
//        digitalWrite(redPin, HIGH);
//        togglestate=1;}
//        else {
//          digitalWrite(redPin, LOW);
//          togglestate=0;}
//          break;
//      }
//    irrecv.resume();
//    }


}
```
- [Control LED light with remote control](https://youtu.be/T26Hd_U4Uo4)

- Use ultrasonic sensor to control the speed of dragon dance machine  
I tried to use ultrasonic sensor to control the speed of dragon dance machine, but the speed didn't change at all.  
I took a long time and found out that I need to press the button every time I want to change the speed of it.  
- Code 2  
```cpp
#include <IRremote.h>
const int RECV_PIN = 4;
const int redPin = 8;
int outputValue=0;
int togglestate = 0;

const int motorPin = 9;  //
int motorspeed = 100;

IRrecv irrecv(RECV_PIN);
decode_results results;
int trigPin = 7;    // Trigger
int echoPin = 6;    // Echo
long duration, cm;

void setup() {
  irrecv.enableIRIn();
  pinMode(redPin, OUTPUT);
  pinMode(motorPin, OUTPUT);
  Serial.begin (9600);
  //Define inputs and outputs
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
}

void loop() {
  if (irrecv.decode(&results)){  
        switch(results.value){
          case 0xFFA25D:
              Serial.print("Jingyu button 1");
              Serial.println("\t Ready to start");  
              digitalWrite(redPin, HIGH);
              analogWrite(motorPin, 0);  // set motor speed to 0 = OFF
          break;
         
          case 0xFF30CF:
              Serial.println("Jingyu button 2: MOTOR ON");
               digitalWrite(trigPin, LOW);
              // if this analogWrite command is in this location, the motor will run when this button is pushed 
              // it will be controlled by remote control - the speed will be controlled by the unltrasonic sensor
              analogWrite(motorPin, motorspeed);             
              digitalWrite(redPin, LOW);
          break;
          case 0xFF18E7:
              Serial.print("Jingyu button 3: ");
              Serial.println("\t What is supposed to happen when this button is pushed?!?");   // answer the question if you want help with this!
              // add other functions here to execute when this button is pushed
              analogWrite(motorPin, 0); // set motor speed to 0 = OFF
            break;
          case 0xFFFFFFF:
              Serial.println("nothing?");
              //analogWrite(motorPin, 0); // set motor speed to 0 = OFF
              digitalWrite(redPin, HIGH);
              analogWrite(motorPin, 0);  // set motor speed to 0 = OFF
          break;     
      }
    irrecv.resume();
    }


// ULTRASONIC SENSOR CODE ==============================================
// The sensor is triggered by a HIGH pulse of 10 or more microseconds.
  // Give a short LOW pulse beforehand to ensure a clean HIGH pulse:
  digitalWrite(trigPin, LOW);
  delayMicroseconds(5);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
 
  // Read the signal from the sensor: a HIGH pulse whose
  // duration is the time (in microseconds) from the sending
  // of the ping to the reception of its echo off of an object.
  pinMode(echoPin, INPUT);
  duration = pulseIn(echoPin, HIGH);
 
// Convert the time into a distance
  cm = (duration/2) / 29.1;     // Divide by 29.1 or multiply by 0.0343
 
  Serial.print(cm);
  Serial.println("cm");
 
  outputValue = constrain(cm, 5, 200); 
  outputValue = map(outputValue, 5, 200, 59, 200); 
  motorspeed = outputValue;  // assuming that the ultrasonic sensor is supposed to control speed this value will control the motor speed

    Serial.print("motorspeed: ");
    Serial.println(motorspeed);  // use these println to debug the code - this value should be always changing.
  
  delay(250);

// ULTRASONIC SENSOR CODE ==============================================
    
 
}
```
- [The speed of dragon dance machine doesn't change](https://youtu.be/lm0o3Ums7AU)  

- Final Project Video  
- [Final Project Video](https://www.youtube.com/watch?v=r9gRIa30qtI)  
