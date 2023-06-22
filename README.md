# Documentacion 2do Parcial
![ArduinoTinkercad (1)](https://github.com/TomasCampos26/ParcialMontacargas/assets/123908697/d69e5246-4c8f-49a0-a250-39338888852d)


## Integrantes 
- Campos Tomás

## ⏰ Proyecto: 
![image](https://github.com/TomasCampos26/parcial2/assets/123908697/ca1e38c2-1a75-4c7b-bee6-10e49c4ff7aa)


## Descripción
El proyecto trata de una simulación de una alarma. El objetivo del proyecto
es realizar una alarma de incendio utilizando Arduino, que detecte los cambios de temperatura
y active un servo motor en caso de detectar un incendio.
Se muestra por medio de un display LCD la temperatura actual y la estacion del año.

## Funciones principales:

~~~ C (lenguaje en el que esta escrito)

/* 1. Esta función se encarga de convertir la lectura del sensor a °C, mostrarla en el display LCD junto
con la estación del año.
Y en el caso de que la temperatura suba a mas de 60°C accionar la alarma y mover el servo motor */
  
  void encenderSistema()  
{
  int lecturaSensor = analogRead(A0);
  int conversor = map(lecturaSensor, 20, 358, -40, 125);
  digitalWrite(LED_ROJO, LOW);
  digitalWrite(LED_VERDE, HIGH);
  
  lcd.clear();
  lcd.setCursor(0, 0);
  lcd.print("ESTACION: VERANO"); 
  lcd.setCursor(0, 1);
  lcd.print("TEMP: "); 
  lcd.setCursor(6, 1);
  lcd.print(conversor);
  delay(500);
  
  if (conversor > 59)
  {
    lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print("ALERTA ALARMA");
    digitalWrite(LED_ROJO, HIGH);
    digitalWrite(LED_VERDE, LOW);
    servo.write(0);
    delay(1000);
    servo.write(180);
    delay(1000);     
  }
}

/* 2. Esta función se encarga de apagar los leds y avisar por display que el
sistema está apagado */
  
void apagarSistema()
{
  digitalWrite(LED_VERDE, LOW);
  digitalWrite(LED_ROJO, LOW);
  delay(100);
  lcd.setCursor(0, 0);
  lcd.print("Sistema apagado");
}

~~~

🎨

~~~ C (lenguaje en el que esta escrito)
/*
PROGRAMA PRINCIPAL
*/

#include <IRremote.h>
#include <Servo.h>
#include <LiquidCrystal.h>

// CAMPOS TOMAS - DIV J <>

#define RS 12
#define EN 11
#define D4 5
#define D5 4
#define D6 3
#define D7 2
#define sensorIR 7
#define LED_ROJO 10
#define LED_VERDE 9
#define tecla_encendido 0xFF00BF00
#define tecla_apagado 0xFD02BF00

LiquidCrystal lcd(RS, EN, D4, D5, D6, D7);
Servo servo;
bool sistema_encendido = false;

void setup() 
{
  Serial.begin(9600);
  lcd.begin(16, 2);
  servo.attach(6);
  IrReceiver.begin(sensorIR);
  pinMode(LED_ROJO, OUTPUT);
  pinMode(LED_VERDE, OUTPUT);
}

void loop() 
{
  if (IrReceiver.decode())
  {
    if (IrReceiver.decodedIRData.decodedRawData == tecla_encendido)
    {    
      sistema_encendido = true;
    }
    else if (IrReceiver.decodedIRData.decodedRawData == tecla_apagado)
    {      
      sistema_encendido = false;
    }    
    IrReceiver.resume();
   }
    if(sistema_encendido == true)
    {
      encenderSistema();
    }
    if(sistema_encendido == false)
    {
      apagarSistema();
    }
     
  delay(50);
}

void encenderSistema()
{
  int lecturaSensor = analogRead(A0);
  int conversor = map(lecturaSensor, 20, 358, -40, 125);
  digitalWrite(LED_ROJO, LOW);
  digitalWrite(LED_VERDE, HIGH);
  
  lcd.clear();
  lcd.setCursor(0, 0);
  lcd.print("ESTACION: VERANO"); 
  lcd.setCursor(0, 1);
  lcd.print("TEMP: "); 
  lcd.setCursor(6, 1);
  lcd.print(conversor);
  delay(500);
  
  if (conversor > 59)
  {
    lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print("ALERTA ALARMA");
    digitalWrite(LED_ROJO, HIGH);
    digitalWrite(LED_VERDE, LOW);
    servo.write(0);
    delay(1000);
    servo.write(180);
    delay(1000);     
  }
}

void apagarSistema()
{
  digitalWrite(LED_VERDE, LOW);
  digitalWrite(LED_ROJO, LOW);
  delay(100);
  lcd.setCursor(0, 0);
  lcd.print("Sistema apagado");
}

~~~

## 🥇 Link al proyecto:
- [Proyecto](https://www.tinkercad.com/things/g8Cci8ZcVkj-copy-of-2do-parcial/editel?tenant=circuits)

---
