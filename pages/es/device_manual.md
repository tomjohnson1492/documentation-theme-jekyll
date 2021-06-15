---
title: Manual de usuariom CanAirIO
tags: [user manual]
keywords: user, user manual, guide, technical manual, manual
last_updated: March 12, 2021
summary: "Manual de usuario de CanAirIO, a nivel de dispositivo y aplicación"
sidebar: english_sidebar
permalink: user_manual_es.html
folder: es
---

# Manual de usuario CanAirIO

CanAirIO en un sensor que mide concentraciones de Material particulado PM2.5, con la opción de Humedad y Temperatura si se le instala el sensor [AM2320](https://www.adafruit.com/product/3721).

La guia completa de como adquirir las partes y la secuencia de armado paso a paso lo encuentran en la [guia de armado de Hacksterio](https://www.hackster.io/canairio/construye-un-sensor-de-calidad-del-aire-bajo-costo-canairio-96f79a)

Todo el desarrollo del Software y las actualizaciones de Firmware son Open Source y lo pueden auditar y descargar del [repositorio en GitHub](https://github.com/kike-canaries)

Tanto los diseños de hardware, el código del software de la app celular y del firmware del aparato son compartidos bajo la filosofa del Open Source y los Datos Abiertos. Los Datos generados por la Red de Monitoreo de la Calidad del Aire CanAir.IO están disponibles en el siguiente mapa : [http//daquina/canairio](http://daquina.io/canairio/) aporte de la comunidad [Un/loquer](https://unloquer.org/) y los datos pueden ser visualizados en http://influxdb.canair.io:8000/


![Imagen de portada](/docs/images/canairio_portada.jpg)

## Encendido

Para encender el sensor, mover a la posición ON el switch (hacia la derecha) si el sensor tiene bateria, si no cuenta con bateria (estación fija) solo basta con conectar el adaptador de 5V al puerto USB.

![Imagen puerto USB](/docs/images/canairio_usb.jpg)

## Indicadores en Pantalla

Indicadores para un sensor con LCD Display


![Imagen LCD](/docs/images/canairio_lcd_es.jpg)


PM2.5.EMOTICON 
Esta es una interfaz que comunica con una serie de emoticones el estado de la calidad del aire, una carita feliz :-) indica una buena calidad del aire, una carita triste una mala calidad del aire :-( una carita enojada una dañina calidad del aire. 

Concentración instantanea
Es el valor de la concentración de PM2.5 que registra el sensor cada segundo


Concentración PM2.5 ug/m3 
Éste indicador es el valor promedio de material particulado medido en microgramos por metro cubico (ug/m3) en el lapso de tiempo que se programe el sensor. El CanAirIO mide concentraciones desde 0 ug/m3 hasta 1000 ug/m3.

Indice de Color
El indice de color es una escala adimensional que asigna un color a un rango determinado de material particulado asi: 
    entre 0 y 12 ug/m3 le asigna el color verde (green) 
    de 12 ug/m3 hasta 35 ug/m3 le asigna el color amarillo (yellow) 
    de 35 ug/m3 hasta 55 ug/m3 le asigna el color naranja (orange), 
    de 55 ug/m3 hasta 150 ug/m3 Rojo (Red), 
de 150 ug/m3 hasta 250 ug/m3 es Violeta (Violet)

Si quiere aprender sobre el Index Color la EPA la Agencia ambiental de los Estados Unidos tiene un muy buen sitio en https://www.airnow.gov/education/


## Recarga de Batería

Para recargar la batería se necesita alimentar el sensor por el puerto de alimentación USB y tener el switch en posición ON ésta aacción enciende un led de color azul que indica el estado de carga de la batería. Se debe usar un adaptador de 5V preferiblemente a 1A o más, se puede usar el cargador de un telefono celular. Es recomendable se use un cargador de buena calidad.

![Imagen puerto USB](/docs/images/canairio_usb.jpg)


---
---

# Aplicacion Celular
La App oficial de CanAirIO se puede descargar del [PlayStore](https://play.google.com/store/apps/details?id=hpsaturn.pollutionreporter) la App funciona solo para el sistema operativo Android Versión 4.1 en adelante, versiones anteriores no son compatibles. En el momento no se cuenta con una App para sistema iOS.

![Panel Mapa](/docs/images/panel_mapa.jpg)

Panel Mapa:
En el panel mapa podemos encontrar los registros de las últimas Mediciones subidas a la base de datos móvil. Para acercar o alejar el zoom se hace con el gesto de los dedos zoom out abrir los dedos, zoom in cerrar los dedos. En ciertos momentos se demora la actulización del mapa debido a que es un servicio externo.

Panel Public
En el panel public, podemos encontrar las grabaciones de los tracks de los últimos recorridos móviles que se han compartido.

Panel Device
En el Panel device se listan todos los dispositivos iOT Bluetooth disponibles en el entorno de la App Móvil, una vez determina el CanAirIO que queremos emparejar se hace click en CONNECT y éste empieza a intercambiar informacion entre la app y el sensor y aparece el panel grabar y el icono rojo.


![Panel recorridos](/docs/images/panel_recorridos.jpg)

-----------------

Panel Grabar
En el panel grabar se van dibujando los valores de PM en función del tiempo al dar click en el icono rojo se inicia la grabación en la SD del telefono celular, la pantalla cuenta zomo la funcionalidad ZoomIN y Zoom OUT para facilitar la visualización cuando hay muchos datos registrados. Al finalizar la medición de debe dar click en el boton negro y esto detendrá la grabación del Track y el recorrido quedará listado en el panel compartir recorrido.

Compartir Recorrido
Para compartir un recorrido se necesita dar click sobre el recorrido que se quiere compartir a la base de datos de Firebase y luego dar click en el icono rojo de compartir, el recorrido así se listará en el panel de recorridos compartidos.


## Grabar Recorrido Móvil

![Panel Grabar](/docs/images/panel_grabacion.jpg)

Para grabar un recorrido móvil debemos tener emparejada la App movil y el sensor, para emparejarlos se da click en el icono de los tres puntos en el panel emparejar disposituvo, ésta función solo aparece si la app se encuentra con el icono de grabar en rojo. 

Aparecen tres opciones; *Unpair* (desemparejar), *Sensor DIY* Guide que llama en el navegador la guia de armado, *FeedBack* para dejar comentarios y reportar fallos y *About* que apunta a la [landing page](https://canair.io/), damos click en Unpair y se debe lanzar el panel de Device y escogemos el Device que queremos usar. Una vez amparejado, se empiezan a grabar los registros en la grafica y podemos empezar la grabación dando click en el icono rojo de grabar.

Para detener la grabación del recorrido de da click en el icono negro de detener la grabación.

En el siguiente link encontrarás un video en donde se explica el proceso de grabación de un recorrido : [Como grabar recorrido](https://www.youtube.com/watch?v=_8zmKYiIqHo)

-------------

## Configurar Estacion Fija

Para configurar una estación fija lo primero que debemos asegurarnos es tener una conexión de WiFi disponible y con clave de acceso. Es importante que si estamos configurando el sensor en una red interna el sysadmin debe abrir el puerto 8086.

El primer paso es grabar en el dispositivo en nombre de la WiFi y el Password,luego movemos el flag a la posición ON Enable WiFi Connection (el flag se pone verde) si la conexión es estable y se ha logeado bien se debe encender el indicador de WiFi OK en el LCD.

En el siguiente video podrás ver el proceso para conectarse a una red wifi : [Conectarse a una red WiFi](https://youtu.be/qP-70XzjtNQ)

![Panel Estacion Fija](/docs/images/panel_estacion_movil.jpg)

Intervalo de muestreo
El sensor, de fábrica puede registrar mediciones de PM2,5 cada segundo pero para el caso de una estación móvil la tasa de muestreo es demasiado alta y consume muchos recursos de almacenamiento en los servidores, la recomendación es que la tasa de muestreo para una estación móvil sea de 60 segundos y para recorridos móviles de 5 segundos.

### Nombrar la Estación

Actualmente el firmware permite darle prácticamente cualquier nombre a la estación, en el futuro el nombre será asignado automáticamente ésto para evitar errores en los registros. 

Se sugiere que el nombre del sensor tenga la siguiente semántica: 

*CO_CO-DC_Ciudad_Localidad_ZipCode_MacAdress*


CO - Pais Colombia
CO-DC - Departamento
Ciudad - Ciudad
ZipCode - Codigo postal
MacAdres - Los cuatro últimos digitos del registro que aparece en el panel Device cuando se llama al sensor

**ATENCIÖN** - En caso de tener que resetear por alguna razón el sensor, el nombre de la estación debe ser exactamente igual al grabado en primera instancia, de lo contrario cualquier error en la sintaxis crearia un nuevo registro en la Base de Datos InfluxDB*.

Ahora solo falta mover el Flag de InfluxDB a ON (posicion en verde) para que los datos se publiquen, si el sensor está grabando bien los datos se debe activar el indicador de Grabado de datos OK que son las dos flechitas en el LCD.

Save current location
Para grabar la localización de Latitud y Longitud de la ubicación de el sensor solo hace falta poder en posición ON el flag save current location.

Reboot Device
Para reiniciar el sensor desde la aplicación celular solo hace falta poner en la posición ON el flag y confirmar el comando REBOT.

Factory Reset
Si por alguna razón necesita hacer un formateo de fábrica del sensor como de la aplicacion celular solo hace falta poner en la posición ON el flag Factory Reset, tenga en cuenta que al hacer esta acción se borran todos los datos del log del sensor. 

Si requiere atención en Soporte tenemos un Canal en Telegram en donde se le puede brindar apoyo en cualquier momento.

[Canal de Soporte en Telegram](https://t.me/canairio)

# Descargo de Responsabilidad

La Red ciudadana de monitoreo de calidad del aire CanAirIO no se hace responsable por malas operaciones con el equipo, el sensor debe ser alimentado por una fuente regulada de 5V (como las de los telefonos celulares) 

En situaciones en que el sensor se use en exteriores éste debe estar protegido de la intemperie, en el foro pueden encontrar algunos ejemplos de como [proteger al sensor de la intemperie](https://foro.canair.io/d/10-dise-os-de-cajas-protectoras-para-uso-en-exteriores) sin afectar su funcionamiento   

La Red Ciudadana de Monitoreo de calidad del Aire CanAirIO pone a disposición de sus usuarios su infraestructura de Datos pero es responsabilidad del usuario resguardar y hacer Backup de los datos, la Red CanAirIO no se hace responsable por perdida de datos en el servidor y/o en cada una de las terminales configuradas.

Creative Commons
V. 01 03/11/2020


# Posiciones correctas de operacion**

Los sensores de material particulado requieren que se dispongan en unas posiciones determinadas para hacer una buena lectura del registro, cada fabricante tiene diferentes posiciones, a continuación se indicarán las posiciones correctas para los sensores SP30 Sensirión, SNGCJA5 Panasonic y PMS7003 PlanTower.

### Sensirion

Si en nuestro CanAir.IO tenemos un sensor Sensirion (SP30) las posiciones correctas para un funcionamiento óptimo son :+1: 

![Sensirion horizontal](/docs/images/sensirion_horizontal.png)

![Sensirion Lateral](/docs/images/sensirion_lateral.png)

![Sensirion Vertical](/docs/images/sensirion_vertical.png)

### Panasonic


### Plantower


# Redes Sociales y Recursos 

1.Landin Page https://canair.io/es
2. Canal de Soporte https://t.me/airqco
3. App Movil AppStore Android https://play.google.com/store/apps/details?id=hpsaturn.pollutionreporter&hl=en
4. CanAirIO Instagram https://www.instagram.com/canairq/
5. CanAirIO Facebook https://www.facebook.com/canairq/
6. Repositorio en GitHub https://github.com/kike-canaries
7. CanAirIO YouTube https://www.youtube.com/channel/UCwxcQKEEe4Iv35zXE0H6jtQ
8. Grafana Estaciones Fijas http://influxdb.canair.io:8000/d/xRQpZACWk/fixed-stations?orgId=1&refresh=5s
9. Cos4Cloud CanAirIO site https://cos4cloud-eosc.eu/citizen-science-innovation/cos4cloud-citizen-observatories/canairio/
10. Album de Fotos https://photos.google.com/u/1/share/AF1QipOwv1e3dW9-I4cOYjKqUle2D4L3Spj6AkoJBYwWzwVUlleWiqyte8p6UAyiQG8e1A?key=Q24zSVdCMzlmYXFkVGNhQ29nWmZGcTJpMlRDbmp3
11. CanAirIO Foro https://foro.canair.io/
12. Wiki un/loquer/CanAirIO http://wiki.unloquer.org/personas/brolin/proyectos/agentes_calidad_aire/cooperaciones/aqa-canairio#inventario_uncanairio
13. CanAirIO Twitter https://twitter.com/canairq

