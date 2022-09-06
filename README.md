# Detector-de-sintomas-COVID

# Introducción


A raíz de la pandemia de COVID-19, la implementación de medidas para evitar la propagación de la infección provocó que la inventiva de los ingenieros, tecnológos y científicos se pusieran en marcha para diseñar dispositivos que permitieran la medición de parámetros de salud que determinaran si una persona estaba infectada o libre de virus. Los parámetros que se usan para determinar de forma rápida la probable infección (sin usar una prueba PCR) son la temperatura corporal y la saturación de oxigenación en la sangre, estos parámetros si no están dentro de un rango aceptable dan una idea sobre la salud de las personas y por lo tanto se restringe el acceso a sitios públicos o donde haya hacinamiento. En este ejercicio se crea un prototipo que mide la saturación de oxigeno en la sangre, la temperatura corporal y el ritmo cardíaco con ayuda de 2 sensores: el max30102 y el MLX90614. 

# Resumen

Este repositorio contiene la información necesaria para crear un prototipo que detecta los sintomas de COVID, el prototipo consta de un detector de oxigenación y ritmo cardíaco MAX30102 y un sensor de temperatura LMX90614. El sistema de adquisición de datos está compuesto por los sensores conectados a un microcontrolador ESP32CAM (programado en arduino) que se conecta a internet vía WIFI, los datos recolectados se almacenan en una base de datos local MySQL y enviados a un flow de node-red mediante el protocolo MQTT.  

# Material necesario
- Sensor MAX30102
- Sensor LMX90614 
- Controlador ESP32cam
- Modulo Adaptador usb a serial ttl ftdi
- Cables jumper
- Protoboard
- Cable serial

# Software necesario
- Ubuntu 22 (https://ubuntu.com/download/desktop)
- Arduino IDE (https://www.arduino.cc/en/software) corriendo en Ubuntu
- Mosquitto (https://mosquitto.org/download/) corriendo en Ubuntu
- Node-red (https://nodered.org/docs/getting-started/local)
- Programa para conectar sensor MAX30102 y LMX90614 al ESP32 y enviar datos al broker local 
[Programa en  arduino](https://github.com/raymundosoto/Detector-de-sintomas-covid/tree/main/CREACIon%20JSON%20MQTT%20MAX30102%20MLX/ESP21CAM-MQTT-MLX90614-MAX30102-JSON)
- MySQL para crear la base de datos local [Instrucciones de creación de base de datos](https://github.com/raymundosoto/Detector-de-sintomas-covid/blob/main/SQL/Instrucciones%20para%20crear%20la%20base%20de%20datos)
- Flow de node red [Flow de node red](https://github.com/raymundosoto/Detector-de-sintomas-covid/blob/main/Flow%20node-red/flows_8_detector_covid_publicacion_BBDD.json)
- Flow de node-red para adquisición, envío y visualización de datos en el broker local y de la base de datos 
- Biblioteca MAX3010x de sparkFun [link biblioteca](https://github.com/sparkfun/SparkFun_MAX3010x_Sensor_Library)
- Biblioteca [PubSubClient](https://pubsubclient.knolleary.net/) en arduino
- Biblioteca LMX90614 [Link de la biblioteca](https://github.com/adafruit/Adafruit-MLX90614-Library)

# Instruccciones
![imagen](https://user-images.githubusercontent.com/72757419/187573107-653a4561-568b-4068-9646-10dc60edecbc.png)

# Funcionamiento

# Resultados
Creación y uso de la base de datos en MySQL
![imagen](https://user-images.githubusercontent.com/72757419/187574025-9b3504ee-6e6f-4a58-b1dd-9f1a8c45ee52.png)

Se muestra resultado parcial de la conexión del sensor de ritmo cardíaco y saturación de oxígeno y la publicación de los datos obtenidos en el broker local

![imagen](https://user-images.githubusercontent.com/72757419/187573521-e76cece2-9470-4769-b323-be9b27def10d.png)

![imagen](https://user-images.githubusercontent.com/72757419/187573484-3e68f795-2336-47c3-8e7b-0e598da07c00.png)

 ## Circuito con los dos sensores conectados y funcionando
 ![imagen](https://user-images.githubusercontent.com/72757419/188005261-45574a60-0b0b-4210-af0f-2ba0a6f4e2ca.png)
 
 Envío de datos a MQTT de forma local y el monitor serial de arduino
 ![imagen](https://user-images.githubusercontent.com/72757419/188006328-121bc36c-6858-41d4-9767-5b65328300f3.png)

Dashboard parcial 

<p align="center">
<img src="https://github.com/raymundosoto/Detector-de-sintomas-covid/blob/main/dashboard1.png" width=50% height=50%>
</p>

Se modificó para incluir un botón de diagnóstico y se cambió el color del tema
<p align="center">
<img src="https://github.com/raymundosoto/Detector-de-sintomas-covid/blob/main/dashboard2.png" width=50% height=50%>
</p>

Flow de Node-red
![imagen](https://user-images.githubusercontent.com/72757419/188715635-0cf0204b-2c6b-42f1-8929-8cfa18d2adb6.png)
Dashboard final
![imagen](https://user-images.githubusercontent.com/72757419/188715815-6996f098-c3d1-401f-b151-3d5a51580fc2.png)

Inserción de datos en la base de datos
![imagen](https://user-images.githubusercontent.com/72757419/188720846-3fb17dbb-3e1e-4e76-859f-feac6d70cf50.png)

# Evidencia

# Conclusiones

# Bibliografía

- Biblioteca adafruit MLX90614. (2021, agosto). Github. Recuperado 6 de septiembre de 2022, de https://github.com/adafruit/Adafruit-MLX90614-Library
- Maximintegrated. (s/f). MAX30102 High-Sensitivity Pulse Oximeter and Heart-Rate Sensor for Wearable Health. https://datasheets.maximintegrated.com/en/ds/MAX30102.pdf
