A SABER 
Bastante util a la hora de comprometer sistemas

COMANDO find

Se usa para hacer busqueda de archivos

Ejemplos practicos

find / -name passwd 2>/dev/null = Le estamos indicando que busque
desde raiz los archivos llamado passwd y que los accesos denegados no aparezcan
![[Pasted image 20240522160906.png]]
find / -user root -writable 2>/dev/null = Le estamos diciendo que busque 
desde raiz los archivos en los que el propietario sea root y tengan permisos de escritura
![[Pasted image 20240522161629.png]]
find / -name "Archivo"\* = Para cuando no sabemos el nombre exacto de un archivo 
![[Pasted image 20240522161950.png]]