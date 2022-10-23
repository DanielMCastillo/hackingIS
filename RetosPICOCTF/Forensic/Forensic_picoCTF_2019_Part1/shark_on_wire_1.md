# USERNAME -> amcdanymx

## Shark on wire 1

#### Description

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

  
#### PISTAS
- Try using a tool like Wireshark
- What are streams?


#### SOLUCIÓN
En este reto vemos que está enfocado a los paquetes de red, podemos analizar los distintos paquetes de navegación de red con la herramienta wareshark que ya viene incluida en Kali Linux

La bandera es: 
```

**  

amcdanymx@kali:~/picoCTF/forensic/sharkonwire1

 $ wget https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap

--2022-10-10 17:48:41--  https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap

Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8

Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.

Petición HTTP enviada, esperando respuesta... 200 OK

Longitud: 239455 (234K) [application/octet-stream]

Grabando a: «capture.pcap»

  

capture.pcap             100%[==============================================>] 233.84K   805KB/s en 0.3s    

  

2022-10-10 17:48:42 (805 KB/s) - «capture.pcap» guardado [239455/239455]

  

amcdanymx@kali:~/picoCTF/forensic/sharkonwire1

 $ ls

capture.pcap

amcdanymx@kali:~/picoCTF/forensic/sharkonwire1

 $ file capture.pcap

capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)

amcdanymx@kali:~/picoCTF/forensic/sharkonwire1

 $ man wireshark

amcdanymx@kali:~/picoCTF/forensic/sharkonwire1

 $ wget https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap

--2022-10-10 17:50:39--  https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap

Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8

Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.

Petición HTTP enviada, esperando respuesta... 200 OK

Longitud: 239455 (234K) [application/octet-stream]

Grabando a: «capture.pcap.1»

  

capture.pcap.1           100%[==============================================>] 233.84K   631KB/s en 0.4s    

  

2022-10-10 17:50:40 (631 KB/s) - «capture.pcap.1» guardado [239455/239455]

  

amcdanymx@kali:~/picoCTF/forensic/sharkonwire1

 $ ls

capture.pcap  capture.pcap.1

**


```

Descargamos el archivo que se nos da, lo metemos a una carpeta que preferamos, en mi caso la carppeta de los retos de forensic, y abrimos nuestro wareshark en Kali, buscamos los paquetes con extension de TDP
Podemos hacer un filtro o recorrer de uno en uno:


```
picoCTF{StaT31355_636f6e6e}

```