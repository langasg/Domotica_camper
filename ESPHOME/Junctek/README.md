# Grupo Telegram --> https://t.me/domotica_camper


## Material Utilizado

### ESP32 https://s.click.aliexpress.com/e/_Evd27Kb
### SHUNT JUNCTEK KGF https://s.click.aliexpress.com/e/_ExIFMGy
### SHUNT JUNCTEK KHF https://s.click.aliexpress.com/e/_EJzoOna

## Preparación HW
Connecta  pin A del termianl del junctek al pin RX del esp32
Connecta  pin B del termianl del junctek al pin TX del esp32
Connecta el pign GND al GND del esp32

## PASOS


1. Descargar codigo yaml, dependiendo del modelo de ShuNT -->  https://github.com/langasg/Domotica_camper/blob/main/ESPHOME/Junctek/kgf.yaml o https://github.com/langasg/Domotica_camper/blob/main/ESPHOME/Junctek/khf.yaml
2. Modificar variables con datos XXXXXX segun corresponda
3. Flashear esp32. Para esto puedes seguir estos tutoriales --> https://github.com/langasg/Domotica_camper/blob/main/ESPHOME/README.md
