# ESP32+DHT22
Reporte de Práctica: Uso de ESP32 con sensor DHT22
## Objetivo de la práctica
El objetivo de esta práctica es aprender a utilizar la placa ESP32 en conjunto con el sensor de temperatura y humedad DHT22, para leer y visualizar los valores de temperatura y humedad en el monitor serie. Este ejercicio permite comprender cómo interactúan estos componentes y cómo se puede obtener información ambiental de manera sencilla utilizando programación en Arduino.
## Material y equipo utilizado
- Placa ESP32: Una microcontroladora de bajo costo con capacidad Wi-Fi y Bluetooth.
- Sensor DHT22: Sensor digital utilizado para medir la temperatura y humedad en el ambiente. Ofrece mediciones precisas en un rango de 0-100% de humedad y -40°C a 80°C de temperatura.
- Plataforma Wokwi: Herramienta de simulación en línea para circuitos electrónicos, que permite emular el comportamiento del código sin necesidad de hardware físico.
## Diagrama de conexión
El pin DHT_PIN del sensor DHT22 está conectado al GPIO 15 de la ESP32.
Se utiliza una resistencia de pull-up de 10k ohmios en la conexión entre el pin de señal del DHT22 y el pin GPIO de la ESP32.

![Texto alternativo](https://github.com/ZurielO/ESP32-DHT22/blob/main/imagen_2024-12-15_145545256.png) 

## Descripción del código
El código de Arduino que se utiliza para esta práctica está basado en la biblioteca DHTesp, que facilita la comunicación con el sensor DHT22. A continuación se explica el funcionamiento del código:



 #include "DHTesp.h
const int DHT_PIN = 15; // Pin de conexión del sensor
DHTesp dhtSensor; // Instancia del sensor

void setup() {
  Serial.begin(115200); // Inicialización del puerto serie
  dhtSensor.setup(DHT_PIN, DHTesp::DHT22); // Configura el sensor DHT22 en el pin especificado
}

void loop() {
  TempAndHumidity data = dhtSensor.getTempAndHumidity(); // Obtiene datos de temperatura y humedad
  Serial.println("Temp: " + String(data.temperature, 1) + "°C"); // Muestra la temperatura
  Serial.println("Humidity: " + String(data.humidity, 1) + "%"); // Muestra la humedad
  Serial.println("---"); // Separador de lecturas
  delay(1000); // Espera 1 segundo antes de tomar otra lectura
}

## Explicación del código:
Librería DHTesp: Se incluye la librería DHTesp.h que permite la interacción con el sensor DHT22.
Configuración del sensor: En la función setup(), se configura el pin donde está conectado el DHT22 y se inicializa el sensor con la función dhtSensor.setup().
Lectura de datos: En el ciclo loop(), el código obtiene la temperatura y la humedad mediante dhtSensor.getTempAndHumidity() y las muestra en el monitor serie con Serial.println().
Tiempo de espera: El delay(1000) asegura que el programa espere 1 segundo entre lecturas consecutivas.
##Resultados esperados
Al ejecutar este código en la plataforma Wokwi o en un entorno físico con la ESP32 y el sensor DHT22, se espera que se muestren continuamente en el monitor serie los valores de temperatura y humedad, actualizándose cada segundo.

Por ejemplo, en el monitor serie, los resultados deberían aparecer de la siguiente manera:

---
Temp: 52.6 °C

Humidity: 57%

---
![Texto alternativo](https://github.com/ZurielO/ESP32-DHT22/blob/main/imagen_2024-12-15_144454105.png?raw=true)

Los valores de temperatura y humedad serán diferentes dependiendo del entorno en el que se simule o se ejecute el código.

## Conclusión
Esta práctica demuestra cómo utilizar el sensor DHT22 para medir parámetros ambientales como la temperatura y la humedad, y cómo integrar estos valores en un sistema de monitoreo con la placa ESP32. A través de la simulación en Wokwi, hemos podido verificar el funcionamiento del sensor sin necesidad de contar con hardware físico. Esta es una habilidad fundamental para proyectos de monitoreo ambiental y automatización en el Internet de las Cosas (IoT).
