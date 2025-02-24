Grupo Telegram --> https://t.me/domotica_camper

JK BMS https://s.click.aliexpress.com/e/_EIZ1VaT
ESP32 https://s.click.aliexpress.com/e/_Evd27Kb

Repo fuente (Source Repository) --> https://github.com/syssi/esphome-jk-bms/tree/main



TUTORIAL

TUTORIAL
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
      

6.  Descargar (https://github.com/langasg/Domotica_camper/blob/main/esp32-ble-jk-ap.yaml) modificar la mac y la configuración WiFi.
   
9. Ejecutar en un terminal.
 
            esphome run esp32-ble-jk-ap.yaml
#1. Instalar python --> https://www.python.org/downloads/
#2. Instalar esphome Ejecutar en un terminal de pip3 install esphome
#3. Instalar git  --> https://git-scm.com/book/en/v2/Getting-Started-Installing-Git 
#4. Descargar fichero .yaml ---> https://github.com/langasg/Domotica_camper/blob/main/esp_jk_ble_ap.yaml
#5. Modificar mac, datos wifi, version protocol, añadir AP. Se han añadido comentarios en los parametros a modificar.
#6. Ejecutar en un terminal.   esphome run esp_jk_ble_ap.yaml



#Para los BMS JBD el proceso es el mismo pero se debe realizar bajando el repo de https://github.com/syssi/esphome-jbd-bms.git
#Lo podemos hacer con el comando --> git clone https://github.com/syssi/esphome-jbd-bms.git
