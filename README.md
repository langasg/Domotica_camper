1. Pre-requisitos
    - Computo:
       1. Raspberry pi (Se recomienda 3b o superior)
           https://s.click.aliexpress.com/e/_Ex8kmc7
       2. Mini PC (tipo nuc)
           https://s.click.aliexpress.com/e/_EH5ezVp
    - Conectividad:
        Router con conectividad redes móviles
           https://s.click.aliexpress.com/e/_ExJmTjH
        Propio móvil
    -  Dispositivos:
        (En este punto entraría en juego las necesidades de cada uno y que queremos monitorizar/controlar)
        ESP32
        ESP8266
        Arduino

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

          1. EPEVER
  
       3. SHUNTS:

          1. Junctek KG140F
  
       5. BMS:

          1. JK BMS

                  - https://github.com/syssi/esphome-jk-bms/tree/main

    
