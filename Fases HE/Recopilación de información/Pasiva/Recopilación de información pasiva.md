A SABER
(La recopilación de información trata de obtener la mayor cantidad de información sobre el objetivo, de manera que facilita las siguientes fases de la intrusión de hacking ético.)

Recopilación de información pasiva: 1 Trata de recolectar información sobre un objetivo determinado sin que las actividades realizadas por el analista sean mínimamente detectadas por el objetivo. 2 Es difícil de realizar y a menudo no proporciona resultados importantes. 3 La manera habitual de recolección pasiva es mediante el acceso a información almacenada en lugares públicos llamado OSINT (raramente es de manera individual.)

# **TECNICAS**

1. _**HACKING CON BUSCADORES (Google Dorks)**_

Comandos para buscadores:

-site:udemy.com - Va a filtrar los resultados para que el único dominio sea udemy en la búsqueda.

-site:udemy.com filetype:pdf - Va a filtrar los resultados para que el único dominio sea udemy en la búsqueda y además aparecerán solo los que contengan la extensión pdf.

-”Index of” /”chat/logs” - Son chats que de alguna forma una entidad o organización a dejado expuesta de forma pública y con ese comando realizas una búsqueda aleatoria de todas las web que contienen algo sobre ello.(Para realizar la búsqueda hacia una entidad o organización en concreto bastara con colocar dicho comando y el comando site:XXXX

- inurl:index.php?id=XXX - inurl Busca según el patrón que nosotros asignemos. El id=XX se puede modificar provocando una SQL Injection y poder acceder a la información de dicha pagina. También se puede centrar el tiro poniendo site:XXXX

-allintitle:XXXX - Muestra todas las paginas con dicha palabra

Ejemplo con SQL (el paréntesis lo que hace es filtrar la búsqueda por dichas palabras):

-filetype:sql “MySQL dump” (pass|password|passwd|pwd) site:XXXX

Ejemplo con allintitle:

-site:gov filetype:pdf allintitle:restricted

gov(gobierno)

Mas información de comandos en: [https://www.pabloyglesias.com/google-hacking/](https://www.pabloyglesias.com/google-hacking/)

2. GOOGLE Hacking Database

Consiste en una base de datos publica donde la gente expone los últimos Dorks mas útiles (ya que los mas utilizados las empresas los parchean o cierran)

3. Shodan

Comienza a realizar peticiones a todos los puertos que se encuentran abiertos a Internet de manera que va recibiendo la información y lo que hace es indexarla para poder visualizarlo.

Repositorio de GitHub para shodan tiene una serie de consultas como por ejemplo (Escritorios remotos activos, Webcams, impresoras etc.…)

[https://github.com/jakejarvis/awesome-shodan-queries](https://github.com/jakejarvis/awesome-shodan-queries)

4. Censys

Similar a shodan lo único diferente es como Censys indexa los datos ya que hace un escaneo a traves de zmap y grab lo que hace que encontremos una información diferente a Shodan

5. Whois

Se usa a traves de la terminal(comandos) y hace una busqueda en bases de datos de cada uno de los registros de una dirección ip o dominio.

Ejemplo: whois [edenhawaiano.com](http://edenhawaiano.com)
![[Pasted image 20240519161601.png]]

whois -h (Muestra una lista de todas las herramientas que ofrece whois)

6. [Archive.org](http://Archive.org)

Muestra los distintos estados y cambios antiguos de cualquier pagina web durante todo el tiempo que lleve activa o publica en Internet

7. theHarvester

Es una herramienta sencilla para la recopilación de información pasiva que opera desde la consola.

-d - Apuntar a un dominio

-b - Con que source vamos a buscar y con el que theHarvester va a realizar las peticiones(hay varios ejemplos realizando un -h)

-l - Limite de resultados de búsqueda

-f - Realiza un HTML donde almacena toda la información de forma ordenada encontrada con el source seleccionado y con algunos mas a su vez. Y información mas detallada en algunos casos. Ejemplo -f resultados.html

Ejemplo:
![[Pasted image 20240519161633.png]]
8. Maltego

Es una herramienta parecida a theHarvester pero mas avanzada y compleja, y contiene una interfaz grafica.

Conocimientos importantes para el uso Maltego:

Transformador:Son repositorios donde se almacenan lo datos de cada query o peticion de consultas con la herramienta (el propio maltego proporciona varios tranform hubs

Grafo:Es una especie de lienzo donde nosotros arrastraremos entidades dependiendo de la consulta que queramos realizar la estructura donde se realizan las consultas

Entity Palette: en la Infraestructura es donde están las entidades que son valores que puedo arrastrar al grafo donde cada una de ellas tiene distintos tipos de infomacion a fuentes publicas sobre los que podremos realizar las consultas.

Ejemplo de maltego con mi propio nombre:
![[Pasted image 20240519161715.png]]
