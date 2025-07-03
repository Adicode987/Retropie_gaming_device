#define DHTPIN 2       
#define DHTTYPE DHT22  
#define RED_LED 9      
#define Fan 10      

DHT dht(DHTPIN, DHTTYPE);  

void setup() {
  Serial.begin(9600);
  dht.begin();
  
  pinMode(RED_LED, OUTPUT);
  pinMode(Fan, OUTPUT);
  
  Serial.println("Automatic Temperature Control System");
}

void loop() {
  float temperature = dht.readTemperature();       
  int threshold = 25;
  Serial.print("Temperature: ");
  Serial.print(temperature);
	
  if(temperature >20){
    digitalWrite(RED_LED, HIGH);
  }
  if (temperature > threshold) {
    digitalWrite(Fan, HIGH);  
    digitalWrite(RED_LED, HIGH);
    Serial.println("Cooling ON");
  } else {
    digitalWrite(Fan, LOW);
    digitalWrite(RED_LED, LOW);  
    Serial.println("Cooling OFF");
  }

  delay(2000);  
}
