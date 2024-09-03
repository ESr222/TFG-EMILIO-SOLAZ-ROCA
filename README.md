Control de Robot Seguidor de Líneas

Este proyecto implementa un robot seguidor de líneas que utiliza tres sensores de infrarrojos para detectar y seguir una línea negra sobre un fondo blanco.
El robot ajusta su dirección de movimiento en función de las lecturas de los sensores, utilizando un chip 74HCT595N para controlar los motores.

Descripción del Proyecto

El robot utiliza un microcontrolador para leer las señales de los sensores de línea y controlar los motores a través de un registro de desplazamiento. 
El código está diseñado para que el robot siga una línea negra de manera autónoma, realizando giros y ajustes según sea necesario.

Componentes Utilizados

Microcontrolador: Arduino (o compatible)
Registro de Desplazamiento: 74HCT595N
Motores: Motores DC controlados mediante PWM
Sensores de Línea: Sensores de infrarrojos (conectados a los pines A0, A1, A2)
Otros Componentes: Resistencias, cables, batería

Configuración del Hardware

Conecta los sensores de línea a los pines A0, A1 y A2 del microcontrolador.
Conecta los pines del registro de desplazamiento 74HCT595N según las definiciones en el código (SHCP_PIN, EN_PIN, DATA_PIN, STCP_PIN).
Conecta los motores a los pines PWM (pines 5 y 6).
Alimenta el circuito con una fuente de energía adecuada.

Funcionamiento del Código

El programa lee continuamente los valores de los sensores de línea y ajusta la dirección del robot según la lógica implementada:

Adelante: Si el sensor central detecta la línea y los sensores laterales no.
Giro Izquierda/Derecha: Si los sensores laterales detectan la línea.
Parada: Si todos los sensores detectan la línea (indica una condición fuera de lo común, como un cruce o el final de la línea).
Personalización
Puedes ajustar los valores de referencia de Black_Line para adaptarlos a diferentes condiciones de iluminación y tipos de superficies. 
Además, puedes modificar las constantes de dirección (Forward, Backward, etc.) para ajustar el comportamiento del robot según tus necesidades.

