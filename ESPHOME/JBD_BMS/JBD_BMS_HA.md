Grupo Telegram --> https://t.me/domotica_camper


JK BMS https://s.click.aliexpress.com/e/_EIZ1VaT

ESP32 https://s.click.aliexpress.com/e/_Evd27Kb

Repo fuente (Source Repository) --> [https://github.com/syssi/esphome-jbd-bms.git](https://github.com/syssi/esphome-jbd-bms/tree/main)



TUTORIAL

1. Si usas windows instalar driver, por norma general el chipset que lleva el esp32 es el ch340 si se usa otro se debera instalar el que se use.--- (https://acebott.com/es/wiki/started-arduino/download-ch340-driver-on-windows-system/)
2. 

1. Instalar python --> (https://www.python.org/downloads/) - Para los puntos 1 y 2 (https://esphome.io/guides/installing_esphome.html)
    Para comprobar la correcta instalación, podemos abrir un terminal y ejecutar

         python --version
   
3. Instalar esphome. Ejecutar en un terminal de pip3 install esphome

          
          pip3 install wheel
          pip3 install esphome
   Para comprobar la correcta instalación podemos ejecutar

          esphome --version

   Si no reconce el comando esphome podemos intentar instalarlo de nuevo con el siguiente comando.

          python -m install wheel
          python -m install esphome

 
5. Instalar git  --> (https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
     Link de descarga Windows --> (https://git-scm.com/downloads/win)  
6. Descargar YAML  ---> (https://github.com/syssi/esphome-jbd-bms/blob/main/esp32-ble-example.yaml)

   
7. Modificar fichero  esp32-ble-example.yaml

   Deberemos modificar  MAC del BMS BLuetooth (linea 5)

8. Debemos crear un fichero con nombre secret.yaml en la misma ruta donde tengamos el fichero esp32-ble-example.yaml

       wifi_ssid: MY_WIFI_SSID
       wifi_password: MY_WIFI_PASSWORD

       mqtt_host: MY_MQTT_HOST #IP del Servidor MQTT de Home Assistant
       mqtt_username: MY_MQTT_USERNAME
       mqtt_password: MY_MQTT_PASSWORD
   
         
10. Ejecutar en un terminal, estando en la carpeta donde se encuentre los ficheros yaml.

            esphome run esp32-ble-example.yaml



