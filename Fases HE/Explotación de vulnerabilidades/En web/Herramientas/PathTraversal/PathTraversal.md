A SABER

PathTraversal es una de las vulnerabilidades mas conocidas y sencillas de entender, concretamente esta vulnerabilidad consiste en una inyeccion de codigo pero en este caso el contexto es de una ruta del sistema de ficheros. En muchas ocasiones en Backend de una aplicacion web hace referencia a ciertos archivos que se encuentran dentro del sistema de ficheros de ese servidor web, por lo que podriamos llegar a obtenerlos
![[Pasted image 20240519170322.png]]
![[Pasted image 20240519170331.png]]
Si nos fijamos cuando accedemos en un apartado de esta aplicacion web, en la ruta que nos filtra nos añade ese page=user_info.php y ese user_info.php es un archivo .php que se encuentra en el sistema de ficheros que se encuentra en el servidor web.Por lo que nosotros podriamos llegar a manipular ese filtro al servidor web.
![[Pasted image 20240519170343.png]]
Esto seria un ejemplo que le diriamos a la consulta web que vaya lo mas atras posible para que llegue a la raiz y que filtre ese /etc/passwd donde se encuentra contraseñas asociadas a ese servidor web.
![[Pasted image 20240519170355.png]]
Como vemos nos ha sacado esa ruta que se corresponde a todos los usuarios que tenemos dentro de ese servidor web (en este caso de nuestra maquina ubuntu, y saber que si fuese hacia un servidor windows seria ..\..\..\..\archivo que sea)

En esto que hemos hecho es en lo que se basa esta vulnerabilidad, que es bastante sencilla de hacer.

En estos casos si no hay un control por parte del Backend de como esta implementada esa funcion que obtiene ese archivo del sistema de ficheros, lo que va a ocurrir es que saldremos de esa carpeta mutillidae y iremos a obtener esos archivos que se encuentren dentro del sistema de ficheros