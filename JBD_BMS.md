Grupo Telegram --> https://t.me/domotica_camper


JK BMS https://s.click.aliexpress.com/e/_EIZ1VaT

ESP32 https://s.click.aliexpress.com/e/_Evd27Kb

Repo fuente (Source Repository) --> [https://github.com/syssi/esphome-jbd-bms.git](https://github.com/syssi/esphome-jbd-bms/tree/main)

TUTORIAL SEGMENTADO  --> (https://github.com/langasg/Domotica_camper/blob/main/ESPHOME/README.md)

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
6. Descargar Repositorio  --->git clone https://github.com/syssi/esphome-jbd-bms.git
     En un terminal ejecutamos
   
         git clone https://github.com/syssi/esphome-jbd-bms.git
         cd esphome-jbd-bms
   
7. Modificar fichero  esp32-ble-example.yaml

   Deberemos modificar  mac, datos wifi, version protocol, añadir AP.
   
   MAC: Buscamos la linea y modificamos con nuestra MAC
   
          
              mac_address: 70:3e:97:07:c0:3e
          
   
   WIFI: Buscamos el bloque de wifi: y cambiamos las lineas que hay por
   
          
              wifi:
                ssid: MY_WIFI
                password: MY_PASSWORD
                ap:
                  ssid: AP_BMS
                  password: JBDBMS00
          
   
   MQTT: Si no vas a usar MQTT o no sabes lo que es, dejar las lineas como se muestran a continuación. Si quieres conectar con Openhab o Home assistant tendras que quitar la # y modificar las variables con tu configuracion del MQTT.
   
         
             #mqtt:
             #  broker: !secret mqtt_host
             #  username: !secret mqtt_username
             #  password: !secret mqtt_password
             #  id: mqtt_client
       

7.b   Un ejemplo de como quedaria el codigo finalmente serí el del siguiente link , (https://github.com/langasg/Domotica_camper/blob/main/esp32-ble-jbd-ap.yaml) de hecho podriais bajar este fichero unicamente y modificar la mac y la configuración WiFi.
   
9. Ejecutar en un terminal.

            esphome run esp32-ble-example.yaml
  o
  
            esphome run esp32-ble-jbd-ap.yaml

