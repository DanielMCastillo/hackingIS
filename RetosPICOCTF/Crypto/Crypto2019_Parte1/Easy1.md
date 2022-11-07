# USERNAME -> amcdanymx

#### Description

The one time pad can be cryptographically secure, but not when you know the key. Can you solve this? We've given you the encrypted flag, key, and a table to help `UFJKXQZQUNB` with the key of `SOLVECRYPTO`. Can you use this [table](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) to solve it?.


#### PISTAS
- Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{HELLO}' as the flag.
- Please use all caps for the message.


#### SOLUCIÓN

Descargamos el archivo que nos dan, lo abrimos y vemos que es una tabla, a partir de la tabla deciframos la bandera:

```
**  

picoCTF/easy1 [ ls                                                                                      ] 2:14

picoCTF/easy1 [ wget https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt

--2022-11-07 14:14:16--  https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt

Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8

Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.

Petición HTTP enviada, esperando respuesta... 200 OK

Longitud: 1571 (1.5K) [application/octet-stream]

Grabando a: «table.txt»

  

table.txt                100%[==============================================>]   1.53K  --.-KB/s en 0s  

  

2022-11-07 14:14:17 (44.5 MB/s) - «table.txt» guardado [1571/1571]

  

picoCTF/easy1 [ ls                                                                                      ] 2:14

table.txt

picoCTF/easy1 [ open table.txt                 
```
  
  Al decifrar nos queda la bandera:
  
```
picoCTF{CRYPTOISFUN}
```

