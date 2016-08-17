// Arduino-Sensor-de-Humedad
// Arduino + Sensor Humedad + 2 Leds indicando estado y valor en porcentaje 0 seco 100 Humedo
//Codigo sensor de humedad tipo (soil Moisture) 

int led = 13;
int led2 = 7;
void setup() {
Serial.begin(9600);
pinMode (led, OUTPUT);
pinMode (led2, OUTPUT);
}

void loop() {
int HumedadBruta = analogRead (A0);
/* map = (nombre del valor, Maximo del Valor, Minimo del Valor, Minimo de la nueva escala de medida, Maximo de la nueva escala de medida)
*/
int HumedadReal = map(HumedadBruta, 1023,0,0,100); 
 Serial.println (HumedadBruta);
 Serial.println (HumedadReal);
 delay (100);

if (HumedadReal < 30)
{ digitalWrite (led, HIGH);
}else{
  digitalWrite (led, LOW);
  
}

if (HumedadReal >30)
{ digitalWrite (led2, HIGH);
}else{
  digitalWrite (led2, LOW);
}

}
