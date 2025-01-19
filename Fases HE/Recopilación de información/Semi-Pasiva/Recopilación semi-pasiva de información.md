A SABER
Se basa en el uso de métodos que generen un trafico de red o un comportamiento similar al que una organización suele recibir por lo que si establece un tipo de comunicación con los sistemas que vayamos a tener de objetivo (sin establecer ningún comportamiento que se salga de lo normal,como por ejemplo un login de un cliente, bajar alguna aplicación corporativa…)

# **TECNICAS**

1. FOCA (metadatos)
2. Central Ops

Es un pagina web donde colocando un dominio o ip nos busca información como información en bases de datos whois, escaneo de servicios, y los registros DNS. Los registros DNS es la única información que podemos obtener a través de la recopilación pasiva de datos.

Cuando realizamos una busqueda con ese parametro de DNS Records (Registros DNS) Aparece el fichero de zona DNS el cual contiene información asociada al nombre de dominio o ip

Ejemplo:
![[Pasted image 20240519161914.png]]
3. DNSDumpster

Es una pagina web muy similar a Central Ops pero mas visual la información, tambien nos sirve para contrastar informacion

4. Whireshark

Es una herramienta sniffer con la cual podemos monitorizar la red

Conceptos:

eth0: Es la que nos conecta a Internet

Loopback: Esla interfaz interna

any: Cualquier interfaz

5. TCPDump

Es una herramienta similar a Whiresark pero a traves de la consola de comandos
![[Pasted image 20240519162008.png]]
Comandos:

sudo tcpdump -D: Muestra las interfaces que tiene el sistema y cuales estan activas (lo mismo que Whiresark en la primera pantalla).

sudo tcpdump -i eth0: Selecciona la interfaz en este caso eth0

sudo tcpdump -v -i eth0: -v lo que hace es mostrar mas información sobre las conexiones

sudo tcpdump icmp: Muestra solo la informacion del protocolo seleccionado en este caso icmp