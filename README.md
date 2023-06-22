# Documentacion 2do Parcial
![ArduinoTinkercad (1)](https://github.com/TomasCampos26/ParcialMontacargas/assets/123908697/d69e5246-4c8f-49a0-a250-39338888852d)


## Integrantes 
- Campos Tomás

## Proyecto: 
![image](https://github.com/TomasCampos26/parcial2/assets/123908697/ca1e38c2-1a75-4c7b-bee6-10e49c4ff7aa)


## Descripción
El proyecto trata de una simulación de una alarma. El objetivo del proyecto
es realizar una alarma de incendio utilizando Arduino, que detecte los cambios de temperatura
y active un servo motor en caso de detectar un incendio.
Se muestra por medio de un display LCD la temperatura actual y la estacion del año.

## Función principal
Esta funcion se encarga de prender en el display el numero que le envias por parámetro.

~~~ C (lenguaje en el que esta escrito)
void PrenderDisplay(int numero)
{
  digitalWrite(A, LOW);
  digitalWrite(B, LOW);
  digitalWrite(C, LOW);
  digitalWrite(D, LOW);
  digitalWrite(E, LOW);
  digitalWrite(F, LOW);
  digitalWrite(G, LOW);
  
  switch(numero)
  {
    case 0:
    digitalWrite(A, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(D, HIGH);
    digitalWrite(E, HIGH);
    digitalWrite(F, HIGH);
    break;
    
    case 1:
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH);
    break;
    
    case 2:
    digitalWrite(A, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(G, HIGH);
    digitalWrite(E, HIGH);
    digitalWrite(D, HIGH);
    break;
  
    case 3:
    digitalWrite(A, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(G, HIGH);
    digitalWrite(D, HIGH);
    break;
    
    case 4:
    digitalWrite(F, HIGH);
    digitalWrite(G, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH);
    break;  
    
    case 5:
    digitalWrite(A, HIGH);
    digitalWrite(F, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(G, HIGH);
    digitalWrite(D, HIGH);
    break;  
    
    case 6:
    digitalWrite(A, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(G, HIGH);
    digitalWrite(D, HIGH);
    break;  
    
    case 7:
    digitalWrite(A, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(D, HIGH);
    digitalWrite(E, HIGH);
    digitalWrite(F, HIGH);   
    digitalWrite(G, HIGH);
    break;  
    
    case 8:
    digitalWrite(A, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(D, HIGH);
    digitalWrite(E, HIGH);
    digitalWrite(F, HIGH);   
    digitalWrite(G, HIGH);
    break;  
    
    case 9:
    digitalWrite(A, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(D, HIGH);
    digitalWrite(F, HIGH);   
    digitalWrite(G, HIGH);
    break;
  } 
}
~~~

## 🛗 Link al proyecto:
- [Proyecto](https://www.tinkercad.com/things/2EVauB1FZrG-parcial-montacargas/editel)

---
