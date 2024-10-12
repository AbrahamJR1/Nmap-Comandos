En nmap se pueden hacer escaneos con protocolo tcp y udp 

---------------------------------------
Escaneo udp 

nmap -sU -p- -T5 (IP) -vvv

y ya pones todo lo demas lo que es necesario es poner es el -sU que le estas indicando que es udp.

---------------------------------------

Escaneo de red para ver todas la maquinas adentro de tu red 
nmap -sn ip/24
ejemplo: nmap -sn 192.168.171.0/24

sn -> sirve para escanear  toda la red.


-------------------------------------------

Escaneo tcp

- opciones Nmap 


-sP: sondeo de ping 

-sS: escaneo mas sigiloso

-sC: versiones 

-sV : servicios de los puertos

-p- :analiza todos los puerto 

--spoof-mac: cambia tu direccion mac cuando haces el escaneo 
ejemplo: --spoof-mac 00:11:22:33:44

-n: no hace resolución dns

-vvv: te va diciendo a cada momento lo que encuentra 

--open: servicios abiertos solo 

-T2: vas mas lento

-Pn: no hace ping

-f: envia paquetes de forma fragmentada

-oN: guarda el escaneo en un archivo.

-sVc: versión de servicios que corre.

-sU: Le indicas que son puertos udp.

--top-ports 200: escaneo de los 200 puertos mas comunes-

--min-rate:numero de paquetes que quieres controlar 2000 es el mas recomendado

 

------------------------------------------------
- Escaneo rapido  (Entorno controlado por que es muy ruidoso)

nmap -p- --open -sS -sC -sV --min-rate=5000 -n -vvv -Pn (ip maquina) -oN nombre reporte 

-----------------------------------------------
- 2do Escaneo rapido (Entorno controlado por que es muy ruidoso)

nmap -p- --open -sS --min-rate=5000 -vvv -n -Pn (ip maquina) -oG nombre reporte 

-----------
- Escaneo para evitar firewalls 
Nmap 

**–mtu** -> ajusta el tamaño de paquetes.

**–data-length** -> ajustar la longitud de los datos.

**–source-port** ->configurar manualmente el número de puerto de origen.

**-D** -> permite enviar paquetes falsos a la red para confundir a los sistemas.

**-f**   -> fragmentar los paquetes enviados para que el Firewall no pueda reconocer el tráfico como un escaneo.

**–spoof-mac** -> se basa en cambiar la dirección MAC.

**-sS** -> realizar un escaneo de tipo **SYN** sin establecer una conexión completa.

**–min-rate** -> permite controlar la velocidad de los paquetes.



----------------------------------------------------------

 - Ataque de fuerza bruta con nmap a un puerto 21 ftp

comando

nmap --script=ftp-brute --script-args userdb=user.txt,passdb=rockyou.txt -p 21 (ip maquina atacar) 


userdb=user.txt -> diccionario de usuarios.

passdb=rockyou.txt -> diccionario de contraseñas.

-p 21 significa que es el puerto 21 

--script=ftp-brute significa que es ftp y ataque de fuerza bruta


- Ya que tengas lo usuarios te puedes meter a ftp. 

para meterte es ftp (ip maquina atacar)

ejemplo: ftp 192.168.0.12


Otros protocolos mas usados
- http-brute
- ftp-brute
- mysql-brute
- ms-sql-brute
- smb-brute
- ldap-brute
- pgsql-brute
- pop3-brute

--------------------------------------------------

- Scripts nmap

- Busca vulnerabilidades específicas en el puerto que selecciones. 

nmap --script "vuln" -p445 (ip maquina atacar)


- Ejecuta todos los scripts disponibles en Nmap para el puerto que selecciones.

nmap --script "all" -p445 (ip maquina atacar)

all: son todos los scripts que tiene Nmap
