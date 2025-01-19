
; = Escribes los comandos que quieras separados por ; en una sola linea
EJ:  ls ; whoami

&& = Es lo mismo que el ; con la diferencia que si el comando anterior no es valido no ejecuta los siguientes
EJ:  ls && whoami

|| = En caso de que el primero no funcione ejecutara el siguiente
EJ: lñ || whoami

&> /dev/null = Este operador lo que hace es redirigir el stderr(codigo de error) y el stdout(resultado comando) a esa ruta para que se borre y no aparezca nada
EJ:cat hola.txt &> /dev/null 
UTILIDAD DE ESTE COMANDO 
(SIN USARLO)
![[Pasted image 20240521213340.png]]
USANDOLO
![[Pasted image 20240521213518.png]]
Basicamente oculta lo que hace el programa en la consola de tal forma que no esta en segundo plano

AÑADIENDO UN disown hace que el proceso sea independiente a la consola y aun que 
se cierre la consola siga ejecutando y este en un proceso diferente