1. Pre-requisitos
    - Computo:
       1. Raspberry pi (Se recomienda 3b o superior)
           Raspberry 4 4gb --> https://s.click.aliexpress.com/e/_EHGYk1H
                       8g. --> https://s.click.aliexpress.com/e/_EjRuZHv
       3. Mini PC (tipo nuc)
           https://s.click.aliexpress.com/e/_EH5ezVp
    - Conectividad:
        Router con conectividad redes móviles
           https://s.click.aliexpress.com/e/_ExJmTjH
        Propio móvil
    -  Dispositivos:
        (En este punto entraría en juego las necesidades de cada uno y que queremos monitorizar/controlar)
       1. ESP32.  https://s.click.aliexpress.com/e/_Evd27Kb
       2. ESP8266. https://s.click.aliexpress.com/e/_Ey6mt3l
       3. Arduino

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
4. Conectividad
  Este punto es bastante crítico, ya que por normal general la conexion que tengamos en nuestra autocaravana/camper no va a ser igual que nuestra casa, raro es la compañia con cobertura movil que te da ip fija (ya no solo fija, fuera de un cgnat) y sin eso de nada nos vale abrir puertos.
      Aqui también quiero establecer dos escenarios:
   1. Router 4g/5g: Podemos instalar un router 4g/5g en nuestro vehículo, lo que nos dara la posibilidad de tener un red wifi local y nos dará salida a internet.
   2. Compartir wifi movil: Otro escenario seria el tener un movil como punto de acceso, esto nos da las mismas opciones, y algun extra, como usar ese movil como wallpanel con los diferentes dashboard. También tendrá sus inconvenientes a nivel de rendimiento.

      Tras analizar estas dos situaciones, cada cual qeu elija la que se adapte mejor a sus necesidades.

      Pero seguiremos con el problema de la conectividad, para eso hemos recurrido a una aplicación pero seguro que esto ira cambiando y creciendo la lista de posibilidades

       1. Tailscale: esta aplicación te permite crear un VPN privada punto a punto con todos los dispositivos que añadas ya sean Windows, Linux,MAC, Android,IOS. Todo esto sin la necesidad de ips fijas, dominios dns ni abrir puertos, por lo cual con cualquiera de las dos soluciones anteriores estaremos contentos.
          1. https://tailscale.com

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

    
############################################################################################################################################################################
############################################################################################################################################################################


NOTIFICACIONES

    Uno de los puntos destacados de tener todo controlado desde un servidor es que podamos gestionar nsootros mismo las notificaciones, lo más comodo será uitlizar Telegram

    Voy a intentar hacer un resumen en ambas plataformas (HA y openhab). 
        1. Primero tenemos un bloque común a ambas, tenemos que crear un bot en telegram, es muy sencillo, nos vamos y buscamos en nuestros chats "BotFather", (estar atentos porque algunos piratillas qeu han copiado logo y nombre, se llama como he puesto ni una letra más ni menos y tienes un check azul), tras esto enviamos un "/start" para iniciar el chat con bot, y despues le enviamos "/newbot" para crear el nuevo bot. Nos pedirá el nombre que siempre debe terminar en "bot" y nos devolvera el token, el cual debemos copiarnos.
        2. Configuración en nuestro server:
            1. Openhab
                1. Instalar binding: En Openhab solo tendremos que añadir el binding de telegram configurar el token y el chatid donde queremos que envie los mensajes.
                2. Crear reglas qeu utilicen la funcion TelegramSend

            2. Home Assistant
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
                        
            
