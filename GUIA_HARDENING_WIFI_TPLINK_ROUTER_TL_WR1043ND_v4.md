author: Raúl Cabrera Garcia
summary: Guía Hardening Router Wi-Fi TP-Link TL-WR1043ND v4
id: TRABAJO_3_HARDENING_TP_LINK
categories: codelab,markdown
environments: Web
status: Published
feedback link: Enlace github para los issue

# GUÍA HARDENING ROUTER Wi-Fi TP-LINK TL-WR1043ND v4.

## Página 1
Duration: 00:02:00
![Foto0_TPLINK](img/foto0.jpg)

**Esta es una guía que servirá para reforzar aspectos de seguridad *"hardening"* para este Router Inalámbrico Gigabit N 450Mbps.**
**Por lo tanto espero que sirva para dicho propósito.**

### OPCIONES WIRELESS
![Foto1_TPLINK](img/foto1.jpg)

* ***Wireless Network Name:*** Es recomendable cambiar el nombre de nuestra Wi-Fi:

Positive
: Ej: “WIFI_SEC_1” . Será el SSID que se vea a la hora de buscar nuestra Wi-Fi.

* ***Mode:*** Para elegir qué protocolos Wi-Fi se van a usar. En este caso, mixto entre los estándar *b/g/n*. Si supiéramos que todos nuestros dispositivos son compatibles bajo un mismo estándar y hubiera posibilidad de dicha configuración. Se pondría la opción de 1 o 2 estándares solo.
* ***Channel Width y Channel:*** Con un ancho de *20MHz* sería suficiente, si es cierto que el ancho de *40Mhz* conseguimos mayor velocidad, pero un menor alcance. Pero dependiendo de las interferencias que tuviéramos. Sería recomendable dejarlo en Auto. Así, el mismo Router decidirá qué ancho de banda utilizar. Lo mismo, con el canal por donde emitir nuestra red Wi-Fi.
* ***Enable Wireless Router Radio:*** Sino es totalmente necesario el uso del Wi-Fi. Entonces desactivaremos esta opción, para no emitir una señal Wi-Fi. Porque se decida, que los dispositivos se van a conectar por cable.
* ***Enable SSID Broadcast:*** Desactivamos está opción, así evitaremos a *priori* emitir el nombre de nuestra red Wi-Fi para todo el mundo.

Negative
: Pequeño inconveniente. Tendremos que introducir manualmente el nombre de nuestra Wi-Fi cuando vayamos a conectar un nuevo dispositivo la primera vez.

## Página 2
Duration: 00:02:00

### OPCIÓN WPS
![Foto2_TPLINK](img/foto2.jpg)

* ***WPS:*** Es muy recomendable dejarlo desactivado siempre. O, como mucho usarlo el tiempo imprescindible para conectar rápidamente una serie de dispositivos que queramos tener.

Negative
: Facilita la conexión a la Wi-Fi, ya que simplemente se hace uso de un PIN de pocos números. Pero es bastante inseguro dejarlo encendido. Puesto que se trata de un pin de solo números, facilmente podría ser crackeable.

## Página 3
Duration: 00:02:00

### OPCIONES SEGURIDAD WIRELESS
![Foto3_TPLINK](img/foto3.jpg)

* ***Encriptación Wi-Fi:*** Dependiendo del entorno en el que vayamos a tener nuestra red Wi-Fi, usaremos tipo Personal o Empresa. A día de hoy, ya hay una alta compatibilidad de dispositivos con *WPA2*. Descartamos *WEP*.
	* ***Versión:*** WPA2-PSK
	* ***Encryption:*** AES
	* ***Wireless Password:*** Elegiremos una clave, que no sea la que viene por defecto. Al menos de unos **14 carácteres** *mayúsculas/minúsculas, números y caracteres especiales*. Otra forma podría ser usar partes de una frase de un libro que te guste y generar una clave.
	* ***Group Key Update Period:*** Si lo dejamos a **0**, no estará activado. Si ponemos **30 (segundos) o más**. Este es el tiempo que queremos que pase para actualizar el grupo de claves; que de manera interna realiza **WPA2**, cuando estamos conectados a nuestra Wi-Fi. Son claves generadas aleatoriamente cada cierto tiempo, diferente a la clave que ponemos la primera vez que nos conectamos a nuestra Wi-Fi.
* ***WPA/WPA2 Enterprise:*** Diferencia, se hace uso de un servidor **RADIUS** de autenticación, cuando se quiere conectar un usuario. Dando un añadido de seguridad, puesto que el servidor se encargará de evaluar si dicho usuario tiene permitido el conectarse a la red Wi-Fi pidiendo un usuario y clave, no que conozcas la clave Wi-Fi solo.
	* ***Radius Server IP:*** Dirección IP del servidor RADIUS.
	* ***Radius Port:*** Puerto del servidor *1812*.
	* ***Radius Password:*** Clave para el servidor RADIUS.
	* ***Group Key Update Period:*** Clave para el servidor RADIUS.

## Página 4
Duration: 00:02:00

### OPCIONES FILTRADO DE M.A.C
![Foto4_TPLINK](img/foto4.jpg)

* ***Wireless MAC Filtering:*** Como medida de seguridad, es bueno habilitarlo. Aunque existen técnicas que luego como atacante permiten clonar o suplantar las MAC 's. Es una capa más de seguridad.

Positive
: De está manera *“registramos"* con la MAC a cada *“estación Wi-Fi”*, que tengamos interconectada con nuestro **“Router Wi-Fi”**. Sólo podrán conectarse a ella los que figuren en la lista. También, podemos hacerlo a la inversa indicando cuáles no queremos permitir que se conecten.

* ***Filtering Rules:***
	* ***Deny the stations specified by any entries in the list to access:*** Denegamos las *MAC's* que registramos abajo.
	* ***Allow the stations specified by any entries in the list to access:*** Permitimos las *MAC's* que registramos abajo.

## Página 5
Duration: 00:02:00

### OPCIONES GUEST NETWORK WIRELESS
![Foto5_TPLINK](img/foto5.jpg)

* ***Guest Network Wireless Settings:*** Este es otro apartado, que si no es totalmente necesario, sería recomendable evitar el habilitarlo. Una red Wi-Fi para invitados. Que permite también que estos puedan acceder a tu red local y habilitar un control del ancho de banda. Según como se configure.
* Un primer apartado similar a la configuración que podemos hacer de nuestra Wi-Fi Principal.
* ***Access Time:*** Podemos elegir entre 2 maneras:
	* ***Schedule:*** Decidimos si todos los días las *24h* o en un rango de horas concretas. O días concretos las *24h* o horas en concreto. No queremos que se puedan conectar los invitados.
	* ***Timeout:*** Indicamos las horas y minutos que tendrán los invitados para hacer uso del Wi-Fi, antes de que se les desconecte.

## Página 6
Duration: 00:02:00

### OPCIONES DHCP (RESERVA DE DIRECCIONES IP)
![Foto6_TPLINK](img/foto6.jpg)

* ***DHCP Server:*** Para habilitar un servidor **DHCP** en nuestro Router Wi-Fi. Servirá *IP’s a los dispositivos*.

Positive
: Recomendable en el Rango de *IP's*, limitarlo a un poco más de los dispositivos que creamos que vamos a tener conectados. No tener un rango muy amplio.

* ***Start IP Address y End IP address:*** Comienzo y fin del rango de IP’s.
	* ***Address Lease Time:*** Tiempo en minutos que mantenemos una IP.
	* ***Default Gateway, Default Domain, Primary DNS, Secondary DNS:*** Otros datos que queramos configurar cuando un dispositivo reciba una IP del DHCP.

Positive
: Recomendable en el par de *DNS’s*. Los de **Cloudflare** o un mixto de el propio que tengamos o de nuestra operadora y uno de **CloudFlare**. Default Gateway, indicamos la IP de nuestros Router Wi-Fi.

![Foto7_TPLINK](img/foto7.jpg)

* ***Address Reservation:*** Otra medida de seguridad y recomendable. Sería el reservar y fuera del rango que de el **DHCP**, una serie de direcciones IP’s que queramos tener configurada en los dispositivos de manera estática. Junto a su **MAC**. Será una capa más, a la hora de posibles ataques maliciosos. Intentando suplantar algún dispositivo importante vía el **DHCP**.

## Página 7
Duration: 00:02:00

### OPCIONES ALMACENAMIENTO COMPARTIDO; FTP, MEDIA Y PRINT SERVER. Y CUENTAS DE USUARIO
![Foto8_TPLINK](img/foto8.jpg)

* ***User Account Management:*** En este apartado podemos habilitar tanto la compartición de almacenamiento, un servidor **FTP**, de **Media** y de **Impresión**. 

Negative
: Aquello que no sea imprescindible como medida de seguridad lo ideal es deshabilitar completamente. Si vamos a usarlo, en el caso de almacenamiento compartido, habilitarlo con contraseña robusta. En el caso de un servidor **FTP**, no usar su puerto por defecto sino otro y sino es imprescindible no habilitarlo para que se pueda acceder desde Internet. Y que su *IP* sea reservada y fuera del rango **DHCP**.

Positive
: Tenemos un apartado de administración de cuentas de usuario. Para el acceso a FTP, usar una política de permisos acorde al usuario que vaya a utilizarlo y poner claves robustas.

## Página 8
Duration: 00:02:00

### PORT TRIGGERING
![Foto9_TPLINK](img/foto9.jpg)

* ***Port Triggering:***  Podemos habilitar puertos, para que ciertos servicios públicos que tengamos activos; como un servidor **FTP**. Equipos fuera de la Red o directamente desde Internet.  Que puedan acceder desde otros equipos.

Positive
: Esto es interesante en casos muy concretos y junto con una buena configuración del firewall o que tengamos habilitado una **DMZ**.

Negative
: Si no lo estamos usando es mejor deshabilitar los puertos en específico.

### CONFIGURACIONES UPnP
![Foto10_TPLINK](img/foto10.jpg)

* ***UPnP:*** Aquí, podremos activar/desactivar el *redireccionamiento* de puertos de manera automática, si un dispositivo lo requieren para la comunicación. Para un mejor control, es recomendable realizar apertura de puertos de manera manual.
Pero en algunos casos puede ser laborioso. Y usando este protocolo se abren y cierran los puertos según se requieran. Por lo que si usamos bastantes puertos. Podría ser buena medida activar **UPnP**, al menos para aquellos dispositivos o aplicaciones que no tengamos configurado de manera manual.

## Página 9
Duration: 00:02:00

### OPCIONES DE SEGURIDAD (Opciones Básicas de Seguridad)
![Foto11_TPLINK](img/foto11.jpg)

* ***SPI Firewall:*** Lo dejamos habilitado, realizará un seguimiento de las conexiones de redes que pasan a través del mismo.
* ***VPN:*** Si queremos habilitar una **VPN** en nuestro Router Wi-Fi. Aunque según las compatibilidades que tengan nuestros dispositivos según los distintos protocolos de VPN.

Positive
: Lo ideal sería habilitar “L2TP con IPSec”, si queremos priorizar la seguridad. PPTP, está en desuso aunque sigue siendo popular su uso.

* ***ALG:*** Aquí podremos habilitar/deshabilitar la capa de aplicación de la puerta de enlace. Actuará como un servidor de aplicaciones controlando si permite/deniega cierto tráfico hacia un servidor de aplicaciones. *FTP, TFTP, RTSP(Transmisión en tiempo real) etc..* 

Negative
: Si no son necesarios y no tenemos habilitado por ejemplo un servidor FTP. Mejor deshabilitar estás opciones.

### OPCIONES DE SEGURIDAD (Opciones Avanzadas de Seguridad)
![Foto12_TPLINK](img/foto12.jpg)

* ***Packet Statistics Interval:*** Podemos asignar un intervalo en segundos. Para luego obtenerlas en una estadística.
* ***DoS Protection:*** Si queremos una protección contra DoS. La dejamos habilitada.
* ***Filtros:*** Tenemos varias opciones de filtros para evitar posibles ataques de **“inundación”**.

Positive
: Interesante sería activar alguno de ellos si detectamos que están intentando enviar muchas peticiones de este tipo.

* ***Filtro de “inundación ICMP”, elegimos Packets/Secs***
* ***Filtro de “inundación UDP”.***
* ***Filtros de “inundación TCP”.***
* ***Ignore Ping Packet from WAN Port to Router:*** Sería recomendable habilitar está opción.
* ***Forbid PIng Packet from LAN Port to Router:*** Si no queremos poder realizar *“pings”*, dentro de nuestra LAN. Activaremos la opción.

## Página 10
Duration: 00:02:00

### ADMINISTRACIÓN LOCAL
![Foto13_TPLINK](img/foto13.jpg)

* ***Management Rules:*** Tenemos 2 reglas que permiten que cualquier PC de la LAN, pueda acceder a la administración vía-web del Router. O solo las **MAC’s** que estén listadas.

Positive
: Lo recomendable sería habilitar aquellas **MAC’s** de los *PC’s* que nos interese. Que deban administrar configuraciones del Router.

### ADMINISTRACIÓN REMOTO
![Foto14_TPLINK](img/foto14.jpg)

* ***Remote Management:*** Podremos configurar para que se pueda acceder de manera remota a administrar nuestro Router. En esta opción elegimos el puerto *443* en vez *80*. Que no sea un puerto por defecto. Y en vez de permitir a cualquier IP, pondremos una IP que supiéramos que está autorizada a poder administrarlo de manera remota.

### REGLAS ADMINISTRACIÓN ACL'S
![Foto15_TPLINK](img/foto15.jpg)

* ***Internet Access Control:*** Habilitamos las listas de control de acceso, para dar una capa más de seguridad a nuestro Router Wi-Fi.
* ***Default Filter Policy:*** Podemos definir la política de filtro que por defecto se aplicará.
	* Si permitir paquetes de un host específico que hemos declarado en las *ACL’s* o denegar específicamente lo que hemos dictado en las *ACL’s*.
* ***Podemos ir definiendo las distintas reglas:***
	* Indicando un nombre, **host(IP o MAC)**, **host objetivo** y **cuándo se realizará esa ACL**.
	* ***Status:*** Si la tenemos activa o no.
	* ***Modify:*** Podemos editarla o eliminarla. 

Positive
: Sería buena medida el crear **ACL’s** para controlar quienes queremos que tenga acceso a Internet.

## Página 11
Duration: 00:02:00

### OPCIONES ENLACE ARP'S
![Foto16_TPLINK](img/foto16.jpg)

* ***ARP Binding:*** Podemos habilitar/deshabilitar, la asignación por **ARP**. Sería una buena medida de seguridad, que nuestros dispositivos que están conectados a la Wi-Fi. Los tengamos identificados por pareja de *MAC e IP*, de está manera podemos evitar posibles suplantaciones. Y ponerlo algo más difícil, ya que el intento de *clonación* del conjunto, sería más complicado.

### LISTADO ENLACES ARP
![Foto18_TPLINK](img/foto18.jpg)

### FIRMWARE UPGRADE
![Foto19_TPLINK](img/foto19.jpg)

* ***Firmware Upgrade:*** Mantendremos siempre que se pueda actualizado el firmware de nuestro Router Wi-Fi.

Positive
: Al fin y al cabo, es lo que nos permite darnos una serie de opciones que podemos luego configurar para dejar más seguro el dispositivo. Y cerrar posibles vulnerabilidades que tenga el dispositivo.

## Página 12
Duration: 00:02:00

### OPCIONES RESTAURACIÓN DE BACKUPS
![Foto20_TPLINK](img/foto20.jpg)

* ***Backup & Restore:*** Mantendremos una política de backups de la configuración de nuestro Router. Por si ocurriera algún percance con ella. Y se tuviera que respaldarla.

Positive
: Para ello es bueno realizarlas, comprobarlas y guardarlas en un lugar seguro que no sea cualquier equipo o dispositivo sin cifrar.

### OPCIÓN CLAVE ADMINISTRACIÓN
![Foto21_TPLINK](img/foto21.jpg)

* ***Clave de administración:*** Punto importante y muy recomendable. Cambiar tanto el *usuario y clave* por defecto del Router Wi-Fi, por otras distintas.

### SYSTEM LOG
![Foto22_TPLINK](img/foto22.jpg)
![Foto24_TPLINK](img/foto24.jpg)

* ***System Log:*** Una buena medida de seguridad. Sería habilitar el *Log del Router*.

Positive
: Podemos configurarlo para que nos lleguen ciertos avisos al Correo.

* ***Log Type:*** *DHCP, VPN, SECURITY, FILTER etc…*
* ***Log Level:*** *ERROR, WARNING, NOTICE y ALL*