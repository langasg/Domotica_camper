# Grupo Telegram --> https://t.me/domotica_camper

## Video
[![Domotiza tu camper - Infraestructura ]([link_a_imagen_miniatura.jpg](https://github.com/langasg/Domotica_camper/blob/main/Infraestructura_Server_camper.png))](https://www.youtube.com/watch?v=l5zyDahIfHw)


[https://youtu.be/l5zyDahIfHw](https://youtu.be/l5zyDahIfHw)

## Material

1. Pre-requisitos
    - Computo:
       1. Raspberry pi (Se recomienda 3b o superior)
           1. Raspberry 4 4gb --> [https://s.click.aliexpress.com/e/_EHGYk1H](https://s.click.aliexpress.com/e/_c4kw7IPt)
           2. Raspberry 4 8gb --> [https://s.click.aliexpress.com/e/_EjRuZHv](https://s.click.aliexpress.com/e/_c4kw7IPt)
       3. Mini PC (tipo nuc)
           [https://s.click.aliexpress.com/e/_EH5ezVp](https://s.click.aliexpress.com/e/_c3leNcfh)
    - Conectividad:
        1. Router con conectividad redes móviles
           https://s.click.aliexpress.com/e/_ExJmTjH
           
        2. Propio móvil
             Visitar la seccion --- CONFIGURACION COMPLEMENTO Hass.io Access Point
             Necesitaremos un usb wifi para poder conectar al wifi del movil y crear un AP, donde se conecten los dispositivos  <a target="_blank" href="https://www.amazon.es/EDiMAX-Adaptador-EW-7811UN-USB2-0-150MBPS/dp/B00EO4HMSQ/ref=sr_1_6?crid=CM6OJUK4Z943&amp;dib=eyJ2IjoiMSJ9.y9923hSu-AnlmMwVm7ip_Ir-8t9SmRknxYe6JHYvilZ_r89VUVKYYGJPnaDEyzKs5bWHZgKJtQhH8t1n_wT-Uzz1ASqazJbWDH1aQrInuylRaIBXyTd3PFO1HR2i65kfspWEsyxVLjWe5pIrZbSzLnR87QzXm6kmuG2Pcr1dQjo7LrxLsn2Io2mOY33KgQdfq8Dieqng1-jns_BBZo6EH0qWicVFC1BDhHZRwHR-G4sX2S_tAhKAvOz3emaXhQd1sxuCz-briBM6AdrXMxgfUiT9WVtgL1Unkj-8cUwD8Fs.Dw1rxxw4u1anR3Jrd9pHibCEDThPS5MXDaRLvpXv2CM&amp;dib_tag=se&amp;keywords=edimax+wifi&amp;qid=1720005659&amp;sprefix=edimax+wifi+%252Caps%252C109&amp;sr=8-6&_encoding=UTF8&tag=docamper-21&linkCode=ur2&linkId=98ef76e69c233e7964e67d725bf71676&camp=3638&creative=24630"> USB Wifi Edimax</a>
        3. Router con opcion de dongle 3G/4G
              Rouer  Mango --->https://s.click.aliexpress.com/e/_ExlCiwX
              Dongle Usb (opcional, solo si no qieremos que el router se conecte a un mobil como AP)
                      https://s.click.aliexpress.com/e/_EGpt7JV
    -  Dispositivos:
        (En este punto entraría en juego las necesidades de cada uno y que queremos monitorizar/controlar)
       1. ESP32.  https://s.click.aliexpress.com/e/_Evd27Kb
       2. ESP8266. https://s.click.aliexpress.com/e/_Ey6mt3l
       3. Arduino

## Instalación

2. Instalación Server 
   En el apartado anterior hemos visto que necesitamos unmodulo de computo (RasPi o MiniPC) en el cual necesitamos albergar el server, que va a ser el encargado de recoger todos los datos y realizar los automatismos que deseemos.

      Aquí yo especificaría dos servidores:

   1. Home Assitant  (Raro es la persona de este mundillo que no lo conoce, el soporte sobre este server es inmenso, hay de todo)
      1. Raspberry pi:   https://www.home-assistant.io/installation/raspberrypi
      2. Mini PC:  https://www.home-assistant.io/installation/generic-x86-64
      3. ODroid: https://www.home-assistant.io/installation/odroid
3. Openhab (Menos conocido, tiene menos soporte, pero para las personas que manejan entornos linux da una gran flexibilidad y comodidad, ya que simplemente es un paquete y la base es un raspbian, desde mi punto de vista más ligero que HA)
      1. Raspberry pi: https://www.openhab.org/docs/installation/openhabian.html
      2. Linux: https://www.openhab.org/docs/installation/linux.html
      3. Windows: https://www.openhab.org/docs/installation/windows.html
      4. macOS: https://www.openhab.org/docs/installation/macos.html

## Comunicaicones

4. Conectividad
  Este punto es bastante crítico, ya que por normal general la conexion que tengamos en nuestra autocaravana/camper no va a ser igual que nuestra casa, raro es la compañia con cobertura movil que te da ip fija (ya no solo fija, fuera de un cgnat) y sin eso de nada nos vale abrir puertos.
      Aqui también quiero establecer dos escenarios:
   1. Router 4g/5g: Podemos instalar un router 4g/5g en nuestro vehículo, lo que nos dara la posibilidad de tener un red wifi local y nos dará salida a internet.
   2. Compartir wifi movil: Otro escenario seria el tener un movil como punto de acceso, esto nos da las mismas opciones, y algun extra, como usar ese movil como wallpanel con los diferentes dashboard. También tendrá sus inconvenientes a nivel de rendimiento.

      Tras analizar estas dos situaciones, cada cual qeu elija la que se adapte mejor a sus necesidades.

      Pero seguiremos con el problema de la conectividad, para eso hemos recurrido a una aplicación pero seguro que esto ira cambiando y creciendo la lista de posibilidades

       1. Tailscale: esta aplicación te permite crear un VPN privada punto a punto con todos los dispositivos que añadas ya sean Windows, Linux,MAC, Android,IOS. Todo esto sin la necesidad de ips fijas, dominios dns ni abrir puertos, por lo cual con cualquiera de las dos soluciones anteriores estaremos contentos.
          1. https://tailscale.com

## Dispositivos / Sensores

6. Dispositivos

   1. ESPs:
       1. Reguladores Solares:

          1. EPEVER.   https://s.click.aliexpress.com/e/_EJUewiX
               Tutorial --> https://gist.github.com/gilankpam/d47555970d2e67f41ab062a30347a100
  
       2. SHUNTS:

          1. Junctek KG140F.  https://s.click.aliexpress.com/e/_Ew3qJE3
                Tutorial --> https://community.home-assistant.io/t/home-assistant-tasmota-wemos-mini-r1-battery-meter-kg140f/473969

       3. BMS:

          1. JK BMS   https://s.click.aliexpress.com/e/_EIZ1VaT

               Tutorial --> https://github.com/syssi/esphome-jk-bms/tree/main
     
       4. Openmqttgateway
           1. Theemometro Xiaomi miija. https://s.click.aliexpress.com/e/_EHCHgyt 
           
       5. Victron 
          Para poder controlar dispositivos victron contamos con el siguiente repositorio que nos permitira su control gracias al uso de un esp.
          https://github.com/Fabian-Schmidt/esphome-victron_ble

          Sin necesidad de esp32, directamente conectando con el bluetooth de la propia raspberry.
          
               https://github.com/SWW13/homeassistant-victron-ir-ble
          




## NOTIFICACIONES

Uno de los puntos destacados de tener todo controlado desde un servidor es que podamos gestionar nsootros mismo las notificaciones, lo más comodo será uitlizar Telegram

   Voy a intentar hacer un resumen en ambas plataformas (HA y openhab). 
   1. Primero tenemos un bloque común a ambas, tenemos que crear un bot en telegram, es muy sencillo, nos vamos y buscamos en nuestros chats "BotFather", (estar atentos porque algunos piratillas qeu han copiado logo y nombre, se llama como he puesto ni una letra más ni menos y tienes un check azul), tras esto enviamos un "/start" para iniciar el chat con bot, y despues le enviamos "/newbot" para crear el nuevo bot. Nos pedirá el nombre que siempre debe terminar en "bot" y nos devolvera el token, el cual debemos copiarnos.
   2. Configuración en nuestro server:
      1. Openhab
         1. Instalar binding: En Openhab solo tendremos que añadir el binding de telegram configurar el token y el chatid donde queremos que envie los mensajes.
         2. Crear reglas qeu utilicen la funcion TelegramSend
      2. Home Assistant  -->  https://www.bujarra.com/enviando-alertas-de-telegram-con-home-assistant-o-hassio/
         1. Modificamos el configuration.yaml con el siguiente bloque
                        telegram_bot:
                                                
                                platform: polling
                                api_key: TOKEN_DEL_BOT
                                allowed_chat_ids:
                                - -ID_CHAT
 
                                notify:
                                - name: telegram
                                platform: telegram
                                api_key: TOKEN_DEL_BOT
                                chat_id: -ID_CHAT
                        
                       
         2. Creamos una automatización, puede ser tanto en modo grafico como con un yaml (automations.yaml)
         ```
           - id: '1561334211255'
             alias: Notificación Telegram - Puerta Garaje-Jardin Abierta
             trigger:
             - entity_id: binary_sensor.puerta_garaje_jardin
             from: 'off'
             platform: state
             to: 'on'
             condition:
             - condition: state
             entity_id: device_tracker.hector
             state: not_home
             - condition: state
             entity_id: device_tracker.seila
             state: not_home
             action:
             - data:
             message: La puerta del Garaje-Jardin está abierta
             service: notify.telegram
           ```                        
            
## CONFIGURACION COMPLEMENTO Hass.io Access Point

Este complemento nos proporcionara la posibilidad de crear un AP dodne se conecten nuestros dispositivos y a traves de otro adpatador de wifi nos conectaremos a nuestra salida a internet, lo que nos proporciona esto es poder salir por el wifi de cualquier movil. Para lo cual necesitaremos dos adapatadores de red, uno puede ser el propio de la raspberry pero necesitaremos uno externo, en la seccion de prerequisitos teneis la lista.

```
    "ssid": "AP-NAME",
    "wpa_passphrase": "AP-PASSWORD",
    "channel": "6",
    "address": "192.168.10.1",
    "netmask": "255.255.255.0",
    "broadcast": "192.168.10.255",
    "interface": "wlan0",
    "hide_ssid": "1",
    "dhcp": "1",
    "dhcp_start_addr": "192.168.10.10",
    "dhcp_end_addr": "192.168.10.20",
    "allow_mac_addresses": [],
    "deny_mac_addresses": ['ab:cd:ef:fe:dc:ba'],
    "debug": "0",
    "hostapd_config_override": [],
    "client_internet_access": '1',
    "client_dns_override": ['1.1.1.1', '8.8.8.8']
```



## Proceso configuracion Termometros Xiaomi bluetooth


   Lo que he tenido que hacer es flashear los termómetros con un firmware especial y luego un esp32 le instalas el openmqttgateway y lo configurar contra tu servidor mqtt y ya haces lo que necesites.

       https://s.click.aliexpress.com/e/_EHCHgyt

   En mi caso son estos pero hay que ver cuales son compatibles con openmqttgateway que en su web hay muchos

   Página para flashear el termómetro 
   
      https://atc1441.github.io/TelinkFlasher.html

   Simplemente conectas el termómetro configuras en la parte baja de la web y flasheas, puedes ajustar intervalo y alguna cosilla más, pero sencillo.

      https://docs.openmqttgateway.com/upload/web-install.html
   Página para instalar openmqtt en un esp32, hay que elegir la opción esp32dev-ble, después te conectas al wifi que crea y ya le configuras tu wifi y tu servidor mqtt.





   ## Para realizar la instalación o estudio personalizado por favor contactar langasg@gmail.com
