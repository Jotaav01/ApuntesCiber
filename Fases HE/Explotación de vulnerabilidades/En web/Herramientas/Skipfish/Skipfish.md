A SABER
Skipfish es una herramienta de kali linux la cual funciona por consola, que nos sirve para hacer spidering de forma activa en nuestro navegador

Comandos mas importantes (tener en cuenta que todos estos comando se pueden juntar en una misma linea :

skipfish -O : Este comando lo que nos va ha realizar es no interactuar mucho tiempo con la aplicacion web y con esto que no sea tan intrusivo

skipfish -Y :
![[Pasted image 20240519170446.png]]
Aqui un ejemplo despues de crear una carpeta skipfish_resultados, que lo que hará la herramienta es realizar un escaneo activo de todas las paginas web que puede tener la aplicacion web (Utiliza diccionarios, spidering pasivo, visitas a pagina web para comprobar que existen etc….).

Uno de los consejos importantes en esta herramienta es que podemos cortar el escaneo con Ctrl + C ya que podria tardar mucho y sacar informacion irrelevante en algunos casos
![[Pasted image 20240519170501.png]]
Despues del escaneo veremos que en la carpeta donde le hemos mandado que guarde los ficheros hay varias carpetas, concretamente el mas interesante es el index.html
![[Pasted image 20240519170515.png]]
Veremos que dentro de este index.html nos ha generado un informe de todos los apartados como paginas web, archivos pdf, txt, png…