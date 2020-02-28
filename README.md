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
