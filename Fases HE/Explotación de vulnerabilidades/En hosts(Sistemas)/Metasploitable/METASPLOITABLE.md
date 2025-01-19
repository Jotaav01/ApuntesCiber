A SABER
Payload: Es lo que se va a ejecutar , el codigo que vayamos a inyectar una vez aprovechado el fallo de seguridad para realizar la accion que nos interesa.

Tipos de Payloads:

Singles - Son los que se denominan autocontenidos o autosuficientes, es decir que por ejemplo no necesitan de metasploit para una conexión.

Ejemplos sobre windows:
![[Pasted image 20240519165031.png]]
Stagers - Dependen de metasploit, y son pequeños y sirven para realizar tareas muy especificas que lo que hacen es lanzar es exploit y establecer una conexion con una maquina y lo que devuelven es una conexion reversa.

Ejemplos sobre windows:
![[Pasted image 20240519165043.png]]
Stages - Tambien dependen de metasploit, y es muy parecida a stagers pero la diferencia es que no solo realizan esa conexion reversa sino que tratan de por ejemplo, inyectar una dll en un proceso o inyectar codigo.

Ejemplos sobre windows:
![[Pasted image 20240519165112.png]]
Exploit: Es el programa que va a aprovechar la vulnerabilidad que encontremos hacia un sistema