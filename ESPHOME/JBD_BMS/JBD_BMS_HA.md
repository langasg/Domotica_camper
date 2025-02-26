Grupo Telegram --> https://t.me/domotica_camper


JK BMS https://s.click.aliexpress.com/e/_EIZ1VaT

ESP32 https://s.click.aliexpress.com/e/_Evd27Kb

Repo fuente (Source Repository) --> [https://github.com/syssi/esphome-jbd-bms.git](https://github.com/syssi/esphome-jbd-bms/tree/main)



Pasos previos

Preparacion del entorno (https://github.com/langasg/Domotica_camper/blob/main/ESPHOME/Preparacion_entorno.md)

TUTORIAL


1. Descargar YAML  ---> (https://github.com/syssi/esphome-jbd-bms/blob/main/esp32-ble-example.yaml)

   
2. Modificar fichero  esp32-ble-example.yaml

   Deberemos modificar  MAC del BMS BLuetooth (linea 5)

3. Debemos crear un fichero con nombre secret.yaml en la misma ruta donde tengamos el fichero esp32-ble-example.yaml

       wifi_ssid: MY_WIFI_SSID
       wifi_password: MY_WIFI_PASSWORD

       mqtt_host: MY_MQTT_HOST #IP del Servidor MQTT de Home Assistant
       mqtt_username: MY_MQTT_USERNAME
       mqtt_password: MY_MQTT_PASSWORD
   
         
4. Ejecutar en un terminal, estando en la carpeta donde se encuentre los ficheros yaml.

            esphome run esp32-ble-example.yaml



