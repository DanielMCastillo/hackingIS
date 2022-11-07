# USERNAME -> amcdanymx

#### Description

Download the packet capture file and use packet analysis software to find the flag.

-   [Download packet capture](https://artifacts.picoctf.net/c/201/network-dump.flag.pcap)


#### PISTAS
- Wireshark, if you can install and use it, is probably the most beginner friendly packet analysis software product..

#### SOLUCIÓN

Descargamos el archivo, abrimos el archivo y vemos el flujo de paquetes usando wireshark, son pocos entonces solo seguimos el flujo TCP que son los que más aparecen y encontramos la bandera:

```
**  
  
  

kali :: ~/picoCTF/packetsprimer » wget https://artifacts.picoctf.net/c/201/network-dump.flag.pcap

--2022-11-07 13:24:56--  https://artifacts.picoctf.net/c/201/network-dump.flag.pcap

Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.69, 13.249.74.17, 13.249.74.56, ...

Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[13.249.74.69]:443... conectado.

Petición HTTP enviada, esperando respuesta... 200 OK

Longitud: 778 [application/octet-stream]

Grabando a: «network-dump.flag.pcap»

  

network-dump.flag.pcap   100%[==============================================>] 778  --.-KB/s en 0s  

  

2022-11-07 13:24:56 (23.1 MB/s) - «network-dump.flag.pcap» guardado [778/778]

  

kali :: ~/picoCTF/packetsprimer » ls

network-dump.flag.pcap

kali :: ~/picoCTF/packetsprimer » wireshark network-dump.flag.pcap

^C

kali :: ~/picoCTF/packetsprimer 130 »

  
  
  
  

p i c o C T F { p 4 c k 3 7 _ 5 h 4 r k _ 0 1 b 0 a 0 d 6 }

  
  
**

```

Aparecía separada entonces solo la acomodamos:
```


p i c o C T F { p 4 c k 3 7 _ 5 h 4 r k _ 0 1 b 0 a 0 d 6 }
picoCTF{p4ck37_5h4rk_01b0a0d6}

```
