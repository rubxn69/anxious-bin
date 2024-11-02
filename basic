#include <ESP32Servo.h>

#define TRIG_PIN 12  // Define the pin for the TRIG signal
#define ECHO_PIN 14
#define SERVO_PIN 13

Servo myServo;  // Define the pin for the ECHO signal

void setup() {
  myServo.attach(SERVO_PIN); 
  Serial.begin(115200); // Start serial communication
  pinMode(TRIG_PIN, OUTPUT); // Set TRIG pin as OUTPUT
  pinMode(ECHO_PIN, INPUT);  // Set ECHO pin as INPUT
}

void loop() {
  long duration, distance;

  // Clear the TRIG pin
  digitalWrite(TRIG_PIN, LOW);
  delayMicroseconds(2);

  // Set the TRIG pin high for 10 microseconds
  digitalWrite(TRIG_PIN, HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIG_PIN, LOW);

  // Read the ECHO pin
  duration = pulseIn(ECHO_PIN, HIGH);

  // Calculate the distance in centimeters
  distance = duration * 0.034 / 2;

  // Print the distance to the Serial Monitor
  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");

  if(distance<20){
     myServo.write(95);
  }
  else{
     myServo.write(180);
  }



  // Wait before taking the next measurement
  delay(500); // Adjust as necessary
}
