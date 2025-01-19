Hydra es un cracker de inicio de sesión paralelizado que admite numerosos protocolos para
ataque. Es muy rápido y flexible, y los nuevos módulos son fáciles de agregar.

Sintaxis: hydra [[[-1 INICIAR SESIÓN|-L ARCHIVO] [-p PASS|-P ARCHIVOJ] | [-C ARCHIVOJJ [-e nsr]
[-0 ARCHIVO] [-t.

TAREAS] [-M ARCHIVO [-T TAREAS]] [-w TIEMPO] [-W TIEMPO [-*] [-5 PORTI [-x MIN:MAX:
JUEGO DE CARACTERES] [-c HORA]

[-ISOuvVd46] [-m MODULE_OPT] [servicio: //servidor [: PUERTO][/OPT]]

Opciones:

- 1 INICIO DE SESIÓN o -L ARCHIVO de inicio de sesión con el nombre de INICIO DE SESIÓN, o cargue varios inicios de sesión desde
ARCHIVO
- ﻿D PASS o -P FILE pruebe la contraseña PASS, o cargue varias contraseñas desde
ARCHIVO
- Formato "login:pass" separado por dos puntos del ARCHIVO C, en lugar de las opciones -L/-P
- ﻿M FILE lista de servidores a atacar, una entrada por línea, para especificar puerto

+ TAREAS ejecutar TAREAS número de conexiones en paralelo por destino (predeterminado: 16).
Reducir a -t 4 ssh

detalles de uso del módulo de servicio

-M OPT opciones específicas para un módulo, consulte la salida -U para obtener más información
opciones de línea de comando (AYUDA COMPLETA)

servidor el objetivo: DNS, IP o 192.168.0.0/24 (esto O la opción -M)
atender el servicio para descifrar (consulte a continuación los protocolos admitidos)

orto

algunos módulos de servicio admiten entrada adicional (-U para ayuda del módulo)

- ﻿R restaurar la sesión anterior
- Ignoro la sesión anterior
- ﻿﻿salir del primer par de inicio de sesión/contraseña
- ﻿v Vervose
- ﻿﻿mostrar cada combinación
- ﻿o archivo de salida uset/pass par