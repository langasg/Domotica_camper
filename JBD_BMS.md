Grupo Telegram --> https://t.me/domotica_camper


JK BMS https://s.click.aliexpress.com/e/_EIZ1VaT

ESP32 https://s.click.aliexpress.com/e/_Evd27Kb

Repo fuente (Source Repository) --> [https://github.com/syssi/esphome-jbd-bms.git](https://github.com/syssi/esphome-jbd-bms/tree/main)



TUTORIAL
1. Instalar python --> (https://www.python.org/downloads/) - Para lospuntos1y 2 (https://esphome.io/guides/installing_esphome.html)
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
          
   
   MQTT: Si no vas a usar MQTT o no sabes lo que es, dejar las lineas como se muestran a continuación.
   
         
             #mqtt:
             #  broker: !secret mqtt_host
             #  username: !secret mqtt_username
             #  password: !secret mqtt_password
             #  id: mqtt_client
       
   
9. Ejecutar en un terminal.

            esphome run esp32-ble-example.yaml

