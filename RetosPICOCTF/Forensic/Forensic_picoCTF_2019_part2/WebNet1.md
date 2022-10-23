# USERNAME -> amcdanymx

## Descripción

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

#### PISTAS

- Try using a tool like Wireshark.
- Try using a tool like Wireshark.

## Solución

Hay que ingresar la llave en la herramienta de  wireshark para buscar en los paquetes donde encontramos una imagen con el protocolo GET , simplmenete la extraemos, la guardamos y aplicamos strings donde encontramos la bandera.

```
╭─amcdanymx@kali ~/picoCTF/webnet1

╰─$ ls

╭─amcdanymx@kali ~/picoCTF/webnet1

╰─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap^H

--2022-10-23 14:19:19--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap%08

Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8

Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.

Petición HTTP enviada, esperando respuesta... 404 Not Found

2022-10-23 14:19:20 ERROR 404: Not Found.

  

╭─amcdanymx@kali ~/picoCTF/webnet1

╰─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap       8 ↵

--2022-10-23 14:19:24--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap

Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8

Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.

Petición HTTP enviada, esperando respuesta... 200 OK

Longitud: 92525 (90K) [application/octet-stream]

Grabando a: «capture.pcap»

  

capture.pcap             100%[=============================================>]  90.36K  --.-KB/s en 0.1s    

  

2022-10-23 14:19:25 (776 KB/s) - «capture.pcap» guardado [92525/92525]

  

╭─amcdanymx@kali ~/picoCTF/webnet1

╰─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key

--2022-10-23 14:19:34--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key

Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8

Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.

Petición HTTP enviada, esperando respuesta... 200 OK
**

Longitud: 1704 (1.7K) [application/octet-stream]

Grabando a: «picopico.key»

  

picopico.key             100%[=============================================>]   1.66K  --.-KB/s en 0s  

  

2022-10-23 14:19:35 (57.4 MB/s) - «picopico.key» guardado [1704/1704]

  

╭─amcdanymx@kali ~/picoCTF/webnet1

╰─$ wireshark capture.pcap

 ** (wireshark:9460) 14:20:38.389912 [GUI WARNING] -- FIX Add drag reordering to UAT dialog

^C^C

╭─amcdanymx@kali ~/picoCTF/webnet1

╰─$ open vulture.jpg                                                                                     130 ↵

╭─amcdanymx@kali ~/picoCTF/webnet1

╰─$ open vulture.jpg -n15

xdg-open: unexpected option '-n15'

Try 'xdg-open --help' for more information.

╭─amcdanymx@kali ~/picoCTF/webnet1

╰─$ strings vulture.jpg -n15                                                                               1 ↵

picoCTF{honey.roasted.peanuts}

 )/'%'/9339GDG]]}

 )/'%'/9339GDG]]}

%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz

&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz

╭─amcdanymx@kali ~/picoCTF/webnet1

╰─$

**

```
y encontramos la bandera.
picoCTF{honey.roasted.peanuts}