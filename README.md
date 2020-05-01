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

- [Youtube Video](https://www.youtube.com/watch?v=KcEAxE8rQ0Y)

# week 11
- sketch for final project  
![week11](/final//Week1/IMG_0242.PNG)

![week11](/final//Week1/IMG_0241.PNG)

![week11](/final//Week2/IMG_1791.HEIC)

![week11](/final//Week2/IMG_1791.HEIC)
