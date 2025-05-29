#include <Servo.h> 

#define SOIL_PIN A0         
#define lampuMerah 6         
#define lampuHijau 7         
#define buzzer 8             
#define servoPin 9          

Servo myServo;

void setup() {
    pinMode(lampuMerah, OUTPUT);
    pinMode(lampuHijau, OUTPUT);
    pinMode(buzzer, OUTPUT);

    myServo.attach(servoPin);
    Serial.begin(9600);
    myServo.write(0);
}

void loop() {
    int soilValue = analogRead(SOIL_PIN);
    Serial.print("Kelembapan: ");
    Serial.println(soilValue);

    if (soilValue > 600) {
        digitalWrite(lampuMerah, LOW); 
        digitalWrite(lampuHijau, HIGH); 
        noTone(buzzer);                 
        myServo.write(0);               
    } else {
        digitalWrite(lampuMerah, HIGH);  
        digitalWrite(lampuHijau, LOW);   
        tone(buzzer, 500);               
        myServo.write(90);               
    }

    delay(1000); 
}
