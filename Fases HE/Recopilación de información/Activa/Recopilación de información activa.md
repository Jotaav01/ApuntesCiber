A SABER
Esta fase tiene como objetivo recolectar información sobre un objetivo determinado utilizando métodos que interactúan de forma directa con la organización normalmente mediante el envió de trafico de red. Ya que establece una serie de interacciones especificas que nos sirvan para sacar información. El conjunto de técnicas suelen ser cosa como la identificación de host en una red, análisis de puertos, identificación de servicios que corren en esos puertos… En muchas ocasiones la actividad de este tipo de técnicas suele ser detectada como actividad sospechosa o maliciosa (Se suele detectar con herramientas como WAF, firewall, IDS, IPS…).

La parte negativa es que para este tipo de técnicas requiere un contacto directo con el objetivo para realizarlas ya que son técnicas intrusivas y en muchas ocasiones suelen ser detectadas. Por lo cual no podemos realizar este tipo de técnicas.

# TECNICAS

DESCUBRIMIENTO DE HOST O NODOS

1. NMAP

nmap -sn (IP) - Sirve para identificar host que se encuentran conectados a una red, establece una conexión a distintos puertos.

sudo nmap -sn (IP) - Es lo mismo que la anterior pero es menos intrusiva y mas efectiva, ya que no establece una conexión directa con el host, simplemente manda un paquete ARP a toda la red y nos responde el host de esa dirección IP

nmap -PS (IP) - Nos realiza un análisis de que puertos estan activos o no de esa maquina y decirnos cuales estan levantados o no(Esta tecnica es mas intrusiva y hace bastante mas ruido ya que realiza el análisis a cientos de puertos por lo que genera cientos de paquetes que pueden ser sospechosos hacia una organización

nmap -PS(Puerto) (IP) -p (Puerto) - Realiza el analisis solamente a un puerto en especifico o los que pongamos.

sudo nmap -sS (IP) -p (Puerto) - Realiza un escaneo del puerto seleccionadode una forma menos “ruidosa” en la red que el anterior comando ya que envia una petición y al momento de obtener la información necesaria cierra esa conexión de tal forma que no se intercambian tantos paquetes como en el anterior y obtiene si el puerto esta abierto, cerrado, filtrado

sudo nmap -sS (IP)/24 - Realiza la misma función que el anterior pero a toda la red que se encuentre en el segmento.(Por lo que se lo envia a todos los host o IPs que esten en nuestra red)

sudo nmap -v —reason -sS -oX (nombre del txt) —stylesheet=(URL) (IP) - Realiza la función anteriormente mencionada con el añadido de -v que significa que pedimos mas información sobre dicho analisis, con el —reason significa que solicitamos saber como ha identificado que el puerto esta en ese estado concreto, y por ultimo el -oX que nos importa el analisis a un fichero que le especifiquemos junto al —stylesheet= donde nos creara en el fichero creado un estilo para que sea mas visual el contenido (nmap tiene url predeterminadas en su web).

(Para poder abrir el fichero tenemos que dar permisos de lectura con sudo chmod 777 y abrir con Firefox (Nombre del fichero).En caso de no abrirse poner maquina virtual modo NAT)

Ejemplo del comando:
![[Pasted image 20240519162152.png]]
Ejemplo de un reporte de análisis de puertos:
![[Pasted image 20240519162210.png]]
EN TODOS LOS COMANDOS VISTOS ANTERIORMENTE DEPENDE DE CADA SITUACION REALIZAR UNO U OTRO YA QUE POR EJEMPLO EL -sS NO HACE TANTO “RUIDO” EN LA RED PERO EN DETERMINADAS OCASIONES PODEMOS ENCONTRANOS CON SISTEMAS DE DETECCION EN LA RED QUE CAPAN EL ESCANEO HACIENDO QUE (PUEDAN IDENTIFICARTE TU SISTEMA, EMITEN UNA ALERTA PARA QUE LA GESTIONEN ETC…) SI REALIZAS EL TIPO DE ACTIVIDAD DE DEJAR EL INTERCAMBIO DE PAQUETES A LA MITAD

Analisis de un servicio que se encuentra corriendo en un puerto:

Comandos:
![[Pasted image 20240519162232.png]]
Este comando realiza el escaneo a un puerto/s y aparte saca la versión del servicio que corre en ese puerto por lo que ya podriamos encontrar alguna vulnerabilidad en base a esa versión.Aparte tambien saca el SO
![[Pasted image 20240519162303.png]]
![[Pasted image 20240519162321.png]]
Este comando es el mismo que vimos anteriormente pero en este caso incluye las versiones y el SO de los puertos abiertos de cada IP.Por lo que está técnica es muchísimo mas intrusiva que las que vimos anteriormente ya que requiere mucha interacción con el objetivo.

IDENTIFICACION DEL SO
![[Pasted image 20240519162339.png]]
Obtiene toda la info posible del SO

¿Que es SMB?
Es un protocolo de red que se lleva utilizando varios años en SOs Windows con el objetivo de compartir ficheros, carpetas compartidas, impresoras etc… a diferenteequipos o nodos que se encuentran en una red, nace con un montón de problemas de seguridad.

SMB Enumeración

Comandos:

/usr/share/nmap/scripts en esta ruta se encuentran las Scripts(Tareas automaticas que tiene por defecto nmap)

Ejemplos con scripts SMB:
![[Pasted image 20240519162422.png]]
Realiza un analisis con la script puesta de las carpetas compartidas encontradas en la red con ese nodo.
![[Pasted image 20240519162441.png]]
Realiza un analisis con la script puesta donde a través de esos puertos nos dice información mas especifica del SO

¿Que es SNMP?
Es un protocolo de red que sirve fundamentalmente para gestionar cosas como obtener datos, cambiar aspectos de configuración de dispositivos como un router, un switch o servidores.Y corre en el puerto 161, y funciona por UDP.
SNMP Enumeración

Comandos:
![[Pasted image 20240519162527.png]]
Realiza el analisis a través del puerto 161 que es el de snmp a través de UDP de ahi el -sU

Ejemplo con scripts snmp:
![[Pasted image 20240519162543.png]]
![[Pasted image 20240519162557.png]]
Realiza un analisis por el puerto 161(SNMP) por UDP y en este caso con la script del software a windows donde como vemos saca informacion valiosa como algunas de las aplicaciones que tiene instaladas el sistema junto a su versión.
![[Pasted image 20240519162630.png]]
Con esta script por ejemplo logramos sacar información valiosa como por ejemplo los usuarios que tiene ese sistema.(A los cuales ya se podrían realizar ataques de fuerza bruta de contraseña etc…)
![[Pasted image 20240519162707.png]]
En esta script nos saca información sobre los procesos que estan corriendo al momento
![[Pasted image 20240519162740.png]]
En esta script sacamos información valiosa de que conexiones de red esta estableciendo ese nodo o sistema.(Donde podríamos hacer ataques como hacernos pasar por un sistema o algún servidor al que se este conectando)
![[Pasted image 20240519162803.png]]
Esta script saca información de hardware de ese sistema como el modelo de CPU

SNMP ES UN PROTOCOLO QUE EN LA MAYORIA DE LAS OCASIONES ESTA MAL CONFIGURADO EN MUCHOS SERVIDORES Y PERMITE LA OBTENCION DE MUCHA INFORMACION LO CUAL HACE QUE ESTA SECCION SEA IMPORTANTE YA QUE LA HACE VULNERABLE FACILMENTE