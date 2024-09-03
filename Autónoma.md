# Navegación Autónoma

Este código implementa un sistema de navegación autónoma utilizando un robot que puede detectar y evitar obstáculos. Para lograrlo, se emplea un sensor ultrasónico SR04, un servomotor y un sistema de control de motores basado en un chip 74HCT595N. El objetivo del algoritmo es permitir que el robot se desplace de manera segura evitando colisiones.
Componentes Principales

## 1.	Servo Motor:

o	Se utiliza para orientar el sensor ultrasónico y escanear el entorno en busca de obstáculos.
o	El servomotor se conecta al pin 9 y se configura para trabajar en un rango de 700 a 2400 microsegundos.

## 2.	Sensor Ultrasónico SR04:

o	Mide la distancia a los objetos frente al robot. Utiliza dos pines: Trig (pin 12) para enviar un pulso y Echo (pin 13) para recibir el eco del pulso, permitiendo calcular la distancia.

## 3.	Control de Motores:

o	Los motores del robot se controlan mediante señales PWM enviadas a los pines 5 y 6.
o	Un chip 74HCT595N se utiliza para controlar la dirección de los motores mediante desplazamiento de bits, permitiendo giros y movimientos específicos.

## 4.	Definición de Movimientos:
Se han definido varias constantes para movimientos predefinidos del robot, tales como Forward, Backward, Turn_Left, Turn_Right, entre otros. 
Estos valores se utilizan para manejar la dirección en la que se mueve el robot.

## Función Principal:

El algoritmo sigue un ciclo continuo (loop()) en el que realiza las siguientes tareas:

1.	Medición de Distancia:

o	Se mide la distancia frente al robot utilizando el sensor ultrasónico.

2.	Decisión de Movimiento:

o	Si el robot detecta un obstáculo a 25 cm o menos, se detiene y el servomotor gira para escanear las distancias a la derecha e izquierda.
o	Dependiendo de las distancias medidas, el robot toma una decisión:
	Gira hacia la dirección con más espacio libre.
	Si ambas direcciones están obstruidas, el robot realiza un giro completo para buscar un camino despejado.
3.	Movimiento del Robot:

o	El robot avanza si no hay obstáculos cercanos.
o	Si detecta un obstáculo, se detiene, evalúa las distancias laterales y decide la mejor dirección para evitar la colisión.
 
## Detalles de Implementación:

•	Función SR04():
o	Calcula la distancia a un objeto usando el sensor ultrasónico.
•	Función Motor():
o	Controla los motores del robot, ajustando la dirección y velocidad según los parámetros recibidos.

## Conclusión
Este algoritmo es una implementación básica pero efectiva de navegación autónoma, adecuada para robots móviles en entornos controlados.
El uso de un sensor ultrasónico combinado con un servomotor permite al robot evaluar su entorno y tomar decisiones en tiempo real para evitar obstáculos, mejorando su capacidad de moverse de forma autónoma y segura.

## Diagrama de Flujo

![image](https://github.com/user-attachments/assets/3f3b53a3-437f-4546-a4b6-f4f9dfe7a89a)

