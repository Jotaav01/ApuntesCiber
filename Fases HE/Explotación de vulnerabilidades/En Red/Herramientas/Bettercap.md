A SABER
Es una de las herramientas fundamentales en todo lo relacionado con vulnerabilidades o ataques en redes.

Instalacion:

sudo apt-get update

`sudo apt install golang git build-essential libpcap-dev libusb-1.0-0-dev libnetfilter-queue-dev`

`go get -u github.com/bettercap/bettercap`
![[Pasted image 20240519171329.png]]
Una vez terminado el proceso de instalacion si nos conectamos por la ruta que nos indica via web veremos que nos sale para colocar una sesion
![[Pasted image 20240519171347.png]]
En este caso voy a utilizar bettercap por consola de comandos.

Si vemos en esta captura poniendo help nos saca los diferentes tipos de ataque que podemos realizar con la herramienta.(y colocando help “tipo de ataque” nos saca informacion mas especifica de cada uno)

1. Herramienta(Bettercap) ARP-Spoofing o ARP Poisoning
![[Pasted image 20240519171400.png]]
En este primer comando colacaremos la ip de la victima para establecer ese target, y a continuacion arrancar el arp spoof
![[Pasted image 20240519171411.png]]
Aqui se ve que lo que esta haciendo bettercap es lanzar multiples paquetes ARP hasta envenenar la cahe ARP de la maquina victima

CON ESTO LO QUE HAREMOS SERA QUE TODO EL TRAFICO DE RED DE ESA IP PASARA PRIMERO POR NUESTRA MAQUINA, MIENTRAS QUE LA MAQUINA VICTIMA NO NOTARA NINGUN CAMBIO EN SU RED

1. Herramienta (Bettercap) DNS Spoofing
![[Pasted image 20240519171429.png]]
Lo primero lanzaremos el servidor web de apache, y iremos a esa ruta
![[Pasted image 20240519171448.png]]
![[Pasted image 20240519171456.png]]
Borramos el index.html y creamos otro desde el root
![[Pasted image 20240519171508.png]]
Queda algo asi alojado en la pagina web por defecto del servidor apache
![[Pasted image 20240519171525.png]]
De nuevo repetimos los pasos del ARP Spoofing y arrancamos el arp.spoof
![[Pasted image 20240519171546.png]]
Finalizamos el proceso anterior y lo siguiente sera colocar un dominio y despues la ip victima
![[Pasted image 20240519171600.png]]
Y lo lanzamos
![[Pasted image 20240519171614.png]]
Y cuando la maquina victima visite la web de [facebook.es](http://facebook.es) le redirigira a ese pagina web por defecto de nuetro servidor apache (la cual podremos manipular para hacer una replica y obtener las credenciales por ejemplo)