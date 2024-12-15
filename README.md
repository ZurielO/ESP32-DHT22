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
## Descripción del código
El código de Arduino que se utiliza para esta práctica está basado en la biblioteca DHTesp, que facilita la comunicación con el sensor DHT22. A continuación se explica el funcionamiento del código:
