A SABER
Es la fase que se encuentra entre la recopilación de información y la explotación de vulnerabilidades. Esta fase consiste en la identificación de fallos de seguridad que se encuentran presentes en sistemas que se están evaluando.

El tipo de fallos abarca desde errores en la configuración de un servicio hasta vulnerabilidades en determinados servicios que sean públicos y puedan comprometer su integridad.

Enlaces de interes:
Sploitus - sitio donde tambien se pueden encontrar exploits

HERRAMIENTAS Y RECURSOS

1. CVE, CVSS, CPE

CVE es una web donde hay una base de datos en la que gente de todas partes publica las vulnerabilidades encontradas de servicios, versiones, sistemas etc… y en el cual se almacenan en la misma.

Ejemplo de un analisis de vulnerabilidad:
![[Pasted image 20240519163130.png]]
En el primer paso cogemos por ejemplo el analisis del anterior escaneo servicios.xml y copiamos el servicio y lo buscamos en la pagina junto a su versión
![[Pasted image 20240519163149.png]]
En el primer paso cogemos por ejemplo el analisis del anterior escaneo servicios.xml y copiamos el servicio y lo buscamos en la pagina junto a su versión
![[Pasted image 20240519163211.png]]
En la parte Arriba a la derecha encontramos CVSS Scores donde si le damos y buscamos el servicio o sistema que hayamos puesto junto a su versión nos encuentra otras vulnerabilidades, junto a su fecha y el nivel de riesgo que tienen que depende de a que podamos acceder o realizar en ese sistema.
![[Pasted image 20240519163230.png]]
Este es un ejemplo de búsqueda con los riegos que tiene cada vulnerabilidad
![[Pasted image 20240519163248.png]]
El cpe es fundamentalmente un código que nos permite identificar un producto de un fabricante que tiene una versión particular rápidamente. Y con ello ver que versiones se ven afectadas a esa vulnerabilidad asociada.

También existe otra web llamada CVE Details donde de forma mas visual te da información de cada vulnerabilidad, con mas información como en que consiste la vulnerabilidad, incluso los productos que se ven afectados como en los cpe y referencias donde están los exploits públicos.

2. Nmap

Ejemplo comandos:
![[Pasted image 20240519163305.png]]
![[Pasted image 20240519163318.png]]
![[Pasted image 20240519163331.png]]
En este caso la script escogida es desde “[https://nmap.org/book/nse-usage.html”](https://nmap.org/book/nse-usage.html%E2%80%9D) donde hay una categoria de scripts cada una con su explicación.

1. Nessus

Se basas en descubrir las vulnerabilidades realizando una serie de escaneos que van a tratar de identificar todos los servicios que se están corriendo en los diferentes puertos o las tecnologias y versiones que corren por detras de manera que luego podamos compararlos en bases de datos como la anterior CVE

Esta herramienta es la mas usada a nivel mundial en cuanto a analisis de vulnerabilidades.

Importante Nessus tiene una herramienta interesante que es cuando vamos a hacer un escaneo esta la opcion Plugins que su funcion es que cuando sale una nueva vulnerabilidad lo que hace Nessus es crear un pluging que realiza un escaneo especifico para esa vulnerabilidad en concreto

Una vez tengamos una cuenta Essentials en Nessus accederemos a en este caso nuestra red interna y con ello hacer el escaneo

El primer paso será arrancar el servicio de nessus en la consola con /bin/systemctl start nessusd.service
![[Pasted image 20240519163403.png]]
De por si Nessus tiene varias plantillas predeterminadas

ESCANEO BASICO
![[Pasted image 20240519163423.png]]
En este caso seleccionaremos Host Discovery (Descubrimiento de hosts)
![[Pasted image 20240519163438.png]]
Aqui colocaremos un segmento de red
![[Pasted image 20240519163455.png]]
Resultado del escaneo basico de Hosts

ESCANEO AVANZADO

Crearemos un nuevo escaneo y accederemos a la seccion de “Policies” (politicas), una vez creada una politica seleccionaremos en este caso Avanced Scan. (Esto de las politicas sirve para configurar una serie de plugings mas o menos ruidosos dependiendo de lo que queramos para que se quede registrado y poder realizarlo cuando queramos con esas mismas reglas que se pueden modificar en cualquier momento).
![[Pasted image 20240519163513.png]]
![[Pasted image 20240519163528.png]]
En este caso dejaremos los plugings activados
![[Pasted image 20240519163542.png]]
En este caso activamos la opcion de escaneo en aplicaciones web, en cuanto a la configuracion realmente se puede configurar mas o menos ruidoso seleccionando puerto tiempo de espera etc segun uno quiera
![[Pasted image 20240519163559.png]]
La opcion safe checks que se encuentra en “Avanced” es importante saber para que sirve ya que lo que hace es prevenir que Nessus algunos escaneos de vulnerabilidades que son muy intrusivos, y que pueden llegar a romper el target que estamos analizando
![[Pasted image 20240519163645.png]]
Una vez creada la politica crearemos un nuevo escaneo y seleccionaremos la opcion userdefined y el que hayamos creado.
![[Pasted image 20240519163708.png]]
El resultado del escaneo seria este
![[Pasted image 20240519163731.png]]
Pudiendo analizar cada una de las vulnerabilidades que ha sacado y incluso esta la opcion de generar un informe en la zona de “Reports” donde podremos verlas de una forma algo mas comoda