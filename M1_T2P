#define PIR_PIN 2  
#define LED_PIN 13 
#define EXT_LED 7  

volatile bool motionDetected = false;  

void motionISR() {
    motionDetected = true; 
}

void setup() {
    pinMode(PIR_PIN, INPUT);
    pinMode(LED_PIN, OUTPUT);
    pinMode(EXT_LED, OUTPUT);
    Serial.begin(9600);

    
    attachInterrupt(digitalPinToInterrupt(PIR_PIN), motionISR, RISING);
}

void loop() {
    if (motionDetected) {
        digitalWrite(LED_PIN, HIGH);  
        digitalWrite(EXT_LED, HIGH); 
        Serial.println("Motion detected! LEDs ON");

        delay(500); // Stability delay

        digitalWrite(LED_PIN, LOW);
        digitalWrite(EXT_LED, LOW);
        Serial.println("No motion detected. LEDs OFF");

        motionDetected = false; 
    }
}
