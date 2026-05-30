>Module 3: The Deep Freeze (Thermal Monitoring)

>Objective:
 The objective of this module is to monitor temperature using a TMP36 temperature sensor and display the readings on   the serial monitor.

>Components used :
 1. Arduino Uno
 2. TMP36 Temperature Sensor
 3. Breadboard
 4. Jumper wires

>Mars Engineering Brief :
 During  a dust storm, the rover should prioritise power for critical systems such as communication, onboard computers,  and survival heaters.  Non-essential systems can be temporarily turned off to conserve battery power when sunlight is unavailable. The temperature sensor continuously monitors the conditions inside the Electronics Box(E-box). If temperature drops below a  safe limit, the rover can automatically activate emergency heaters to keep the batteries and electronics warm. This helps in preventing the system failure and improves the rover chances of surviving in extreme Martian conditions.

>Code file (in C): [Module_3_The_Deep_Freeze.c](https://github.com/user-attachments/files/28422281/Module_3_The_Deep_Freeze.c)

>Code Explanation :
 Serial.begin(9600) starts serial communication between the Arduino and the computer. Serial.print() is used to        display the sensor readings on the Serial Monitor. Together, they allow the temperature values to be monitored in     real time.

>Tinkercad Simulation Link : https://www.tinkercad.com/things/bSdYxWV6lD4-module-3/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard&sharecode=fALisAzPTJYM2R0XVLloRkq8oOz2s_HG9qqHxbgdWNk

>Code in text :
//Module 3 The Deep Freeze
// C
// Defining Pin`
int sensorPin = A0;

void setup(){
  Serial.begin(9600);
  /*Serial.begin function starts communication between Arduino
  and the computer*/
}

void loop(){
  int sensorValue = analogRead(sensorPin);
  /*Storing the sensor values by reading them from the 
  analog pin using analogRead function*/
  
  float voltage = sensorValue * (5.0 / 1023.0);
  /*This is the standard formula used to convert Arduino's
  analog reading into actual voltage value*/
  /*The Arduino has a 10 bit ADC(Analog to Digital Converter). 
  That means it converts the voltage values 0V to 5V into numbers
  ranging from 0 to 1023*/
  
  /*Printing the voltage values*/
  Serial.print(" Voltage : ");
  Serial.println(voltage);
  
  delay(1000);
}


