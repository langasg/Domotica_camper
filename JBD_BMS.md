Grupo Telegram --> https://t.me/domotica_camper

JK BMS https://s.click.aliexpress.com/e/_EIZ1VaT
ESP32 https://s.click.aliexpress.com/e/_Evd27Kb

Repo fuente (Source Repository) --> https://github.com/syssi/esphome-jk-bms/tree/main



TUTORIAL
1. Instalar python --> https://www.python.org/downloads/
2. Instalar esphome Ejecutar en un terminal de pip3 install esphome

         pip install esphome
   
4. Instalar git  --> https://git-scm.com/book/en/v2/Getting-Started-Installing-Git 
5. Descargar Repositorio  ---> git clone https://github.com/syssi/esphome-jbd-bms.git
     En un terminal ejecutamos
   
         git clone https://github.com/syssi/esphome-jbd-bms.git
         cd esphome-jbd-bms
   
6. Modificar fichero  esp32-ble-example.yaml
7. Debermos modificar  mac, datos wifi, version protocol, añadir AP.
   
   MAC: BUscamos la linea y modificamos con nuestra MAC
   
          
              mac_address: 70:3e:97:07:c0:3e
          
   
   WIFI: Buscamos el bloque de wifi: y cambiamos las lineas que hay por
   
          
              wifi:
                ssid: MY_WIFI
                password: MY_PASSWORD
                ap:
                  ssid: AP_BMS
                  password: BMS
          
   
   MQTT: Si no lo vamos a usar comentamos las lineas
   
         
             #mqtt:
             #  broker: !secret mqtt_host
             #  username: !secret mqtt_username
             #  password: !secret mqtt_password
             #  id: mqtt_client
       
   
8. Ejecutar en un terminal.   esphome run esp_jk_ble_ap.yaml

