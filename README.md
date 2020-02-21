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
