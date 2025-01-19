A SABER
Es una herramienta de consola de comandos (ya instalada en kali), que funciona de manera que por un lado una URL donde haya una serie de campos que va identificar automaticamente como puntos de inyeccion o podemos pasarle incluso una peticion que hayamos interceptado con Burpsuite.

En este ejemplo lo haremos con la ayuda con Burpsuite
![[Pasted image 20240519170639.png]]
Antes de nada pondremos en on el proxy de Burpsuite a interceptar las peticiones
![[Pasted image 20240519170649.png]]
Haremos login una vez este en on Burpsuite
![[Pasted image 20240519170702.png]]
Veremos que nos ha interceptado esta peticion “POST” en este caso
![[Pasted image 20240519170716.png]]
Bien lo que haremos con esta peticion será copiarla en un archivo en el escritorio

Entonces lo que le pediremos a SQLmap es con la peticion que tenemos en ese archivo txt que hemos generado con Burpsuite que trate de encontrar parametros o puntos de inyeccion vulnerables de SQLInjection
![[Pasted image 20240519170729.png]]
En esta sentencia de comandos lo que hacemos es buscar las vulnerabilidades, —flush-session lo que nos hace es que las anteriores peticiones las borre y la haga con esta nueva, y el -r es para indicarle donde esta el archivo request.burp.txt
![[Pasted image 20240519170740.png]]
Veremos que sqlmap lo primero que nos dice es que cuando se ha intentado logear le quiere redireccionar a la pagina home, y por ello nos pregunta si queremos redireccionar o no. En este caso no (la opcion en mayuscula es la opcion por defecto en este caso la Y bastaria con darle enter)
![[Pasted image 20240519170841.png]]
Nos vuelve a preguntar y nos dice la base de datos que hay de fondo es MySQL ¿Quieres saltar los test para ver si descubro cual es la base de datos. Le vamos a dar a si en este caso
![[Pasted image 20240519170853.png]]
Una vez contestamos la anterior a Si nos saltara otra pregunta que si queremos que nos incluya unos analisis un poco mas extensos y intrusivos. En este caso le damos a Si
![[Pasted image 20240519170906.png]]
Vemos que sqlmap nos ha encontrado una vulnerabilidad en el username en este caso. Una vez aqui en este caso cortare el proceso ya que se haria largo.
![[Pasted image 20240519170921.png]]
En esta consulta vemos distintos parametros, cada uno de ellos realiza una funcion que son:

—ignore-redirects : Lo que nos hara es ignorar todas las redirecciones que hemos visto antes pero automaticamente.

—technique : Este comando se trata de la tecnica que vamos a usar en especifico en este caso Blindmap por loque solo haria falta poner la letra B

-p : Le estamos indicando que se centre unicamente en el parametro username

—current-user : Con este comando le decimos que queremos que saque el usuario actual de la base de datos
![[Pasted image 20240519170937.png]]
Aqui vemos que ha sido capaz de obtener el usuario root@localhost que esta ejecutando estas consultas , gracias al comando -p username
![[Pasted image 20240519170948.png]]
Cuando ya hemos obtenido ese usuario, cambiaremos nuestra consulta y como vemos quitaremos el —current-user ya que tenemos el usuario, y le pondremos -U indicando el usuario y añadiremos tambien el comando —passwords que tratara de encontrar las contraseñas asociadas a ese usuario (si la tiene, que en este caso no).

Otro comando que hemos añadido es el —batch que es para que no nos pida tantas cosas como por ejemplo si queremos continuar solo con consultas MySQL, lo hara automaticamente
![[Pasted image 20240519171006.png]]
Como vemos nos da un resultado NULL, debido a que como ya sabemos nuestro user root de esta base de datos MySQL(configurada en nuestro ubuntu) no tiene contraseña.
![[Pasted image 20240519171016.png]]
En esta nueva consulta he quitado lo otro una vez obtenido, y he añadido el —dbs que lo que quiere decir es que queremos obtener el nombre de la bdd y el -v de 3 para que saque mas cosas por pantalla y nos vaya diciendo que va haciendo
![[Pasted image 20240519171029.png]]
Y en el resultado vemos que nos ha sacado que hay 5 bdd
![[Pasted image 20240519171044.png]]
En este comando lo que hara es obtener las tablas que estan dentro de estas bdd mutillidae
![[Pasted image 20240519171056.png]]
Aqui nos estara sacando todas las tablas de la bdd mutillidae

Algo importante a saber sobre todas estas tecnicas con sqlmap es que son muy intrusivas, aqui muestro todo el trafico que generaria con el wireshark, (que como ya sabes todo ese trafico va dirigido a ese servidor al que vayamos)
![[Pasted image 20240519171113.png]]