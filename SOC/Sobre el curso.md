## Servicio DNS:

Almacenan la información en los "archivos de zona". Cada zona almacena una serie de datos que se denominan "registros de recursos" (Resource Records - RR).

- Tipo A: A partir de un nombre de máquina devuelve su IPv4
- Tipo AAAA: A partir de un nombre de máquina devuelve su IPv6
- Tipo NS (Name Server): A partir de un nombre de dominio devuelve los servidores DNS donde está alojado.
- Tipo MX (Mail eXchanger): A partir de un nombre de dominio devuelve el servidor o los servidores de corre electrónico.
- Tipo PTR: A partir de una IP nos devuelve el nombre de la máquina.
- Tipo SOA (Start of Authority): Nos devuelve información técnica sobre la

Hay 3 modelos de SOC:

- In House / Internet SOC Model
- Outsourced SOC Model
- Hybrid SOC Model

Tipos de modelos madurez de un SOC:

- SOC - Capacity Maturity Model
- Systems Security Engineering Capabilility Maturity Model (SSE-CMM)

Formulas de Ataque :

Attack= Motive (Goal) + Method (TTPs) + Vulnerability

Smurf : Es un tipo de ataque que el atacante hace un ping desde una IP victima, para inundar a la maquina

Tipos de escaneo de nmap :

nmap IP - En wireshark aparecera un SYN
