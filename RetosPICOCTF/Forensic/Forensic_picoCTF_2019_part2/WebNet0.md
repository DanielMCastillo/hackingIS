
# USERNAME -> amcdanymx


## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

#### PISTAS

- Try using a tool like Wireshark.
- How can you decrypt the TLS stream?

## Solución

Tenemos que leer los paquetes con la herramienta wireshark y agregar una llave para desencripción de TLS en wireshark para despues buscar en los paquetes TLS, vemos que no la podemos leer al inicio pero con el archivo que contiene la llave si, simplemente al ponerla buscamos el texto con el filttro en la herramienta 
```
**╭─amcdanymx@kali ~

╰─$ wget https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap

--2022-10-23 13:52:06--  https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap

Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8

Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.

Petición HTTP enviada, esperando respuesta... 200 OK

Longitud: 112318 (110K) [application/octet-stream]

Grabando a: «capture.pcap»

  

capture.pcap             100%[=============================================>] 109.69K   588KB/s en 0.2s    

  

2022-10-23 13:52:07 (588 KB/s) - «capture.pcap» guardado [112318/112318]

  

╭─amcdanymx@kali ~

╰─$ ls

bandit    championsliguifile  Documentos  hash  Imágenes  jwt.txt  picoCTF programacion  testing

capture.pcap  Descargas       Escritorio  icpc  isredes   Música   Plantillas  Público   Vídeos

╭─amcdanymx@kali ~

╰─$ file capture.pcap

capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)

╭─amcdanymx@kali ~

╰─$ wireshark capture.pcap

^C

╭─amcdanymx@kali ~

╰─$ wireshark capture.pcap

```
y encontramos la bandera.
picoCTF{nongshim.shrimp.crackers}
