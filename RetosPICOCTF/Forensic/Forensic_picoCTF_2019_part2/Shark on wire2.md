# USERNAME -> amcdanymx

## Descripción

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

## Solución

Hay que seguir el flujo de paquetes UDP del archivo .pcap en wireshark y convertir el numero de los puertos a char
```
**─amcdanymx@kali ~

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

╰─$ wireshark capture.pcap 5**
```

Usamos scapy un script para obtener la bandera
```
from scapy. all import *
packets = rdpcap('capture.pcap')

flag = ' '

for p in packets_
	if UDP in p and p[UDP].dport == 22
		if p[UDP].sport > 5000:
				flag+= chrp[UDP].sport = 5000)

print(flag)
```
Obtenemos la bandera: 

picoCTF{p1LLf3r3d_data_v1a_st3g0}