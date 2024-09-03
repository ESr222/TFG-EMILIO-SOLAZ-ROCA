# Control de Robot con WiFi usando ESP32 y Arduino Uno

Este proyecto permite controlar un robot con ruedas mecanum utilizando un ESP32 como servidor web para enviar comandos al Arduino Uno, que controla los motores del robot.

## Componentes

- ESP32
- Arduino Uno
- Módulo de expansión con chip 74HCT595N para control de motores
- Servo motor
- Sensor de ultrasonido HC-SR04

## Conexiones

### ESP32
- GPIO16 (RX) ← TX del Arduino Uno
- GPIO17 (TX) → RX del Arduino Uno
- GND del ESP32 → GND del Arduino Uno

### Arduino Uno
- Pin 9: Servo motor
- Pin 12: Trig del sensor ultrasonido
- Pin 13: Echo del sensor ultrasonido
- Pins 2, 4, 5, 6, 7, 8: Control de motores y registro de desplazamiento

## Cómo Funciona

El ESP32 actúa como un servidor web, donde puedes acceder a una interfaz con botones para controlar el robot. Al presionar un botón, el ESP32 envía un comando específico al Arduino Uno a través de la comunicación serial. El Arduino Uno recibe estos comandos y controla los motores del robot en consecuencia.

## Instalación

1. Clona este repositorio en tu máquina local.
2. Abre el código `ESP32_Wifi` en el IDE de Arduino y cárgalo en la ESP32.
3. Abre el código `ArduinoUno_Wifi` en el IDE de Arduino y cárgalo en el Arduino Uno.

## Uso

1. Conecta la ESP32 a la red WiFi.
2. Abre un navegador web y accede a la dirección IP de la ESP32.
3. Usa la interfaz web para controlar el robot.

## Driagrama de Flujo

![image](https://github.com/user-attachments/assets/b0d15d54-eb25-4ec4-8844-08cf217788ac)
