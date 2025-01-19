A SABER
Es un proyecto Open Source(codigo abierto) dedicado al estudio (en comunidad) de las vulnerabilidades y riesgos que afectan a las aplicaciones web, cuyo objetivo es determinar y combatir las causas que hacen que el software sea inseguro. ESTA METODOLOGIA ES LA MAS ESTANDAR Y IMPORTANTE EN APLICACIONES WEB
Su metodologia lo que nos va a permitir es definir en orden cada una de las fases y acciones que debemos realizar diciendonos en cada momento que herramientas utilizar, como solventar vulnerabilidades.



OWASP Top 10 - Es un estudio que se realiza cada 4 años y muestra cuales son las vulnerabilidades mas criticas de hoy en dia.

OWASP MVs - Tiene una serie de maquinas virtuales para realizar cualquier tipo de prueba sin tener que hacerlo con una pagina externa.

Tienen varios tipos que son:

Owasp Broken Web Appliccations Project - Es un conjunto de muchas aplicaciones web vulnerables
![[Pasted image 20240519173540.png]]
Web for Pentester (I y II) - Tiene un catalogo de tipos de ataques donde se podran realizar ejercicios a cada uno de esos apartados (tienen algo mas de complejidad que las MVs de OWASP)
![[Pasted image 20240519173556.png]]
DVWA - Es simple al igual que la de OWASP y es recomendable aprender al principio con este tipo de maquinas
![[Pasted image 20240519173611.png]]
Ejemplo de DVWA de kali a Windows server 2022 (tener instalada la herramienta de Wampserver64 en la maquina windows):
![[Pasted image 20240519173632.png]]
Una vez activemos la herramienta Wampserver64 en la maquina windows
![[Pasted image 20240519173645.png]]
Para entrar colocamos admin/password

Abrimos el Burpsuite y desactivamos el intercept
![[Pasted image 20240519173707.png]]
![[Pasted image 20240519173721.png]]
Cambiamos el nivel abajo a la izq en este caso en bajo
![[Pasted image 20240519173734.png]]
generamos una sesion
![[Pasted image 20240519173749.png]]
![[Pasted image 20240519173801.png]]
La enviamos al Secuenciador
![[Pasted image 20240519173813.png]]
Y lo lanzamos
![[Pasted image 20240519173827.png]]
Si lo paramos y lo analizamos nos saldra el nivel 
