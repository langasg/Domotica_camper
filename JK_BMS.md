# Grupo Telegram --> https://t.me/domotica_camper

## Material Utilizado

### JK BMS https://s.click.aliexpress.com/e/_EIZ1VaT

### ESP32 https://s.click.aliexpress.com/e/_Evd27Kb

### Esp32 display https://s.click.aliexpress.com/e/_EJieKBO






## TUTORIAL

Pensado unicamente para bloquear el acceso por Bluetooth a la BMS, Si quieres conectar el bms a Home assistant o Openhab no uses este manual.

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
      

6.  Descargar (https://github.com/langasg/Domotica_camper/blob/main/esp_jk_ble_ap.yaml) modificar la mac del bms (linea 5) y la configuración WiFi (linea 28 a 33).
   
9. Ejecutar en un terminal.
 
            esphome run esp_jk_ble_ap.yaml



##Fuentes

#### Repo fuente (Source Repository) --> https://github.com/syssi/esphome-jk-bms/tree/main
