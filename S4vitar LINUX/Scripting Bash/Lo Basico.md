
El primer paso sencillo es crearlo con esta extension .sh
![[Pasted image 20240522162653.png]]
Le asignamos permisos de ejecucion
![[Pasted image 20240522163025.png]]
Y esta seria una forma de ejecutar el script o poniendo bash script.sh (simplemente he puesto un echo probando en el script)
![[Pasted image 20240522163050.png]]
Otro ejemplo mas util es poniendole un 
ip a | grep eth0 (filtra por palabra)| tail-n 1(busca el parrafo) | awk '{print $2}'(busca el argumento )
![[Pasted image 20240522164106.png]]
Pues este mismo comando se lo ponemos a nuestro script (el $ sirve para que nos devuelva el resultado de un comando)
![[Pasted image 20240522164459.png]]
Resultado
![[Pasted image 20240522164630.png]]
