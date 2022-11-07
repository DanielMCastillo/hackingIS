# USERNAME -> amcdanymx

#### Description

Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/4c996ecfb7fbada15a9799511f24dc99/shark1.pcapng).
  
#### PISTAS
- No hay

#### SOLUCIÓN

Descargamos el archivo, abrimos la herramienta wireshark y vemos el flujo de paquetes, podemos encontrar uno que no tiene encriptación, seguimos ese flujo HTTP y encontramos un archivo con una bandera en formato rot13

```
**  

wiresharkdoo % wget https://mercury.picoctf.net/static/4c996ecfb7fbada15a9799511f24dc99/shark1.pcapng  

--2022-11-07 13:06:14--  https://mercury.picoctf.net/static/4c996ecfb7fbada15a9799511f24dc99/shark1.pcapng

Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142

Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.

Petición HTTP enviada, esperando respuesta... 200 OK

Longitud: 1558808 (1.5M) [application/octet-stream]

Grabando a: «shark1.pcapng»

  

shark1.pcapng 100%   1.49M  1.45MB/s en 1.0s    

  

2022-11-07 13:06:15 (1.45 MB/s) - «shark1.pcapng» guardado [1558808/1558808]

  

wiresharkdoo % ls

shark1.pcapng

wiresharkdoo % wireshark shark1.pcapng

^C

wiresharkdoo %

  
  

 cvpbPGS{c33xno00_1_f33_h_qrnqorrs}

 picoCTF{p33kab00_1_s33_u_deadbeef}

**
```


Desecriptamos de rot13 y obtenemos la bandera
```
 cvpbPGS{c33xno00_1_f33_h_qrnqorrs}

 picoCTF{p33kab00_1_s33_u_deadbeef}
```

