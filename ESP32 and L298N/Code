int motorPin1 = 27; 
int motorPin2 = 26; 
int enablePin = 14; 

const int freq = 30000;
const int pwmChannel = 0;
const int resolution = 8;
int dutyCycle = 200;

void setup() {
  pinMode(motorPin1, OUTPUT);
  pinMode(motorPin2, OUTPUT);
  pinMode(enablePin, OUTPUT);

  ledcSetup(pwmChannel, freq, resolution);

  ledcAttachPin(enablePin, pwmChannel);

  Serial.begin(115200);
}

void loop() {
  ledcWrite(pwmChannel, dutyCycle);  
  digitalWrite(motorPin1, HIGH);
  digitalWrite(motorPin2, LOW);
  Serial.println("Forward");
  delay(5000);

  digitalWrite(motorPin1, LOW);
  digitalWrite(motorPin2, LOW);
  Serial.println("Stop");
  delay(5000);

  digitalWrite(motorPin1, LOW);
  digitalWrite(motorPin2, HIGH);
  Serial.println("Backward");
  delay(5000);
   while (dutyCycle <= 255){
    dutyCycle = dutyCycle + 5;
    delay(500);
  }
  dutyCycle = 200;
}
