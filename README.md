# VIRAC-Vehículo Inteligente Remoto y Autónomo Controlado
VIRAC es un vehículo autónomo a escala 1/12 que integra control remoto, visión por computadora 3D y navegación inteligente. Esta guía está pensada para que un alumno o colaborador pueda montar, configurar y operar el vehículo sin depender del autor original.
#Hardware
#2. Componentes
## 2.1 Componentes electrónicos
| Componente           | Modelo / Detalle   | Función                            |
| -------------------- | ------------------ | ---------------------------------- |
| Jetson               | [modelo exacto]    | Procesamiento de visión y control  |
| PCA9685              | 16-ch servo driver | Control de servos                  |
| Puente H             | BTS7960            | Control de motores DC              |
| IMU                  | [modelo]           | Orientación y movimiento           |
| Cámara 3D            | [modelo]           | Visión por computadora             |
| ESP32 (opcional)     | [modelo]           | Comunicación remota o sensor extra |
| Sensores ultrasonido | [modelo]           | Detección de obstáculos            |

## 2.2 Conexiones
I2C: PCA9685, IMU, sensores

PWM: Servos y control de motores

GPIO: LEDs, botones, comunicación adicional
#Alimentaciòn Energética
-----------------------DIAGRAMA----------------------------
| Componente | Voltaje nominal         | Fuente recomendada            | Comentarios                                            |
| ---------- | ----------------------- | ----------------------------- | ------------------------------------------------------ |
| Jetson     | 5V – 19V (según modelo) | Adaptador de corriente o LiPo | Evitar caídas de voltaje                               |
| PCA9685    | 5V                      | Desde Jetson o fuente externa | Separar fuente si se usan muchos servos                |
| Servos     | 4.8 – 6V                | Batería externa               | Cada servo puede consumir hasta 1A                     |
| Motores DC | 12V                     | Batería Li-ion o LiPo         | Asegurarse de que el puente H soporta corriente máxima |
| Sensores   | 3.3 – 5V                | Fuente común                  | Compatible con Jetson y PCA9685                        |
Recomendaciones:

Usar reguladores de voltaje si hay distintos niveles de alimentación.

Separar la fuente de los servos y motores de la del Jetson para evitar reset inesperado.

Verificar polaridad antes de conectar.

##2.4 Mecánica

Chasis 1/12

Ruedas y motores DC

Soporte para cámara 3D y sensores

Tornillería y piezas impresas (STL)

Ajustes finos mediante tornillos y tuercas

 #  3. Software
## 3.1 Sistema base

Jetson con sistema operativo [Ubuntu + JetPack versión]

Actualización de drivers y CUDA Toolkit

## 3.2 Dependencias

Python 3.x

OpenCV (para visión)

PyTorch / YOLOv5 (detección de objetos)

Bibliotecas para PCA9685, BTS7960 e IMU

## 3.3 Instalación y configuración

Flashear Jetson con el sistema operativo y JetPack

Instalar librerías Python necesarias

Configurar scripts de control remoto y autónomo

Probar comunicación con PCA9685, motores, IMU y cámara 3D

Ajustar parámetros de visión y calibración de servos

# 4. Montaje físico

Montar chasis y ruedas

Instalar motores y puente H

Colocar PCA9685 y conectar servos

Colocar cámara 3D y sensores

Conectar alimentación siguiendo diagrama

Organizar cables y fijar todo con soportes o bridas

# 5. Pruebas y calibración

Verificar que servos respondan correctamente

Comprobar que los motores giren en ambas direcciones

Confirmar lectura de IMU y sensores

Ajustar cámara 3D y calibrar visión

# 6. Mantenimiento y troubleshooting

Revisar conexiones y polaridad

Evitar que el Jetson se reinicie por caída de voltaje

Reemplazo de piezas impresas o tornillería

Documentar cualquier cambio para futuros alumnos
