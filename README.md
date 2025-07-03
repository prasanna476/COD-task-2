# COD-task-2#define relayPin 8

void setup() {
  Serial.begin(9600); // Initialize serial communication for Bluetooth
  pinMode(relayPin, OUTPUT); // Relay control pin as output
  digitalWrite(relayPin, LOW); // Initially OFF
}

void loop() {
  if (Serial.available()) {
    char command = Serial.read(); // Read incoming command

    if (command == '1') {
      digitalWrite(relayPin, HIGH); // Turn ON device
      Serial.println("Device ON");
    } 
    else if (command == '0') {
      digitalWrite(relayPin, LOW); // Turn OFF device
      Serial.println("Device OFF");
    }
  }
}
