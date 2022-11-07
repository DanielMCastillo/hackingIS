# USERNAME -> amcdanymx

#### Description

Decrypt this [message](https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext).


#### PISTAS
caesar cipher [tutorial](https://learncryptography.com/classical-encryption/caesar-cipher)


#### SOLUCIÓN
Descargamos el archivo, leemos dicho archivo y vemos que nos dan una bandera, analizamos y sabemos que está en formato rot13, use una herramienta para decodificar
https://gchq.github.io/CyberChef/ donde tuvimos que rotar varias veces el texto para que tuviera algo de sentido

```
picoCTF/caesar [ wget https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext

--2022-11-07 15:07:15--  https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext

Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8

Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.

Petición HTTP enviada, esperando respuesta... 200 OK

Longitud: 35 [application/octet-stream]

Grabando a: «ciphertext»

  

ciphertext               100%[==============================================>]  35  --.-KB/s en 0s  

  

2022-11-07 15:07:15 (28.8 MB/s) - «ciphertext» guardado [35/35]

  

picoCTF/caesar [ ls                                                                                     ] 3:07

ciphertext

picoCTF/caesar [ cat ciphertext                                                                         
```

Bandera sin rotar
```
picoCTF{ynkooejcpdanqxeykjrbdofgkq}% 
```

  
  Rotada 25 veces:
  
```
picoCTF{crossingtherubiconvfhsjkou}
```