A SABER
Es un proxy de interpretacion, lo que quiere decir es que esta herramienta se va a localizar entre nuestro navegador y la aplicacion web o servidor web al que estamos realizando la peticion, segun varios expertos en seguridad de aplicaciones web, la herramienta mas usada es esta Burpsuite.

Lo primero que habria que hacer para su uso es configurar nuestro navegador para que todas las peticiones que se realicen pasen a traves de Burpsuite (proxy)

Esta herramienta solo recibe informacion de forma pasiva, es decir sin hacer ruido practicamente.

Una vez dentro de BurpSuite

![[Pasted image 20240519165722.png]]

La pestaña de Proxy se puede considerar la mas fundamental ya que describe el comportamiento de esta aplicacion

![[Pasted image 20240519165743.png]]
Antes de nada para que todo funcione tendremos que cambiar la configuracion del navegador de nuestro kali
![[Pasted image 20240519165816.png]]
Iremos abajo del todo
![[Pasted image 20240519165825.png]]

![[Pasted image 20240519165839.png]]
Y configuraremos el proxy de forma manual junto al puerto, que nos indica el burpsuite
![[Pasted image 20240519165909.png]]
En Burpsuite colocaremos el proxy a on para interceptar todas las peticiones
![[Pasted image 20240519165921.png]]
Despues de hacer un ejemplo en la aplicacion web de mutillidae, el proxy nos muestra exactamente la peticion que hemos hecho, por lo que podremos cambiar cualquier parametro que vemos en la peticion
![[Pasted image 20240519165941.png]]
Para reenviar la peticion a nuestro servidor de ubuntu, le damos a Forward

Spidering y Crawling con Burp Suite y skipfhish
![[Pasted image 20240519165958.png]]
En el Burpsuite veremos que tenemos un apartado llamado Target
![[Pasted image 20240519170022.png]]
En este apartado de Target veremos que esta la ip de la maquina host del servidor web de la pagina (en este caso nuestra maquina ubuntu), pues si nos adentramos en el y le damos a mutillidae y seguidamente index.php.

Veremos que Burpsuite nos ha hecho un reconocimiento de todas las paginas web que hay en esta aplicacion web, este reconocimiento se le llama Spidering o Crawling. Todo esto nos sirve para mas tarde seleccionarlas como Target y poder explotar vulnerabilidades en ellas.
![[Pasted image 20240519170039.png]]
Si pulsamos en una pagina veremos que a la derecha saca un codigo con varias informaciones sobre ella, si vemos en esta situacion de spidering se denomina spidering pasivo ya que es lo que nos ha generado Burpsuite por defecto.

En esta ultima version de Burpsuite no se establecen peticiones de forma activa con el servidor, para ello podriamos descargandonos la version .1 de Burpsuite donde esta el apartado de “Spidering”, pero en este caso lo realizaremos desde otra herramienta de kali diferente a Burpsuite llamada “Skipfhish” la cual estara en otro apartado.