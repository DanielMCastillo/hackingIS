# USERNAME -> amcdanymx

## What Lies Whitin

#### Description

 There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?
  
#### PISTAS
- There is data encoded somewhere... there might be an online decoder.


#### SOLUCIÓN


Descargamos el archivo, vemos que es un archivo de imagen, lo abrimos y aparece un edificio, a este tipo de forma de codificar información en una imagen se le conoce como Steganography que implica ocultar información seneible de manera secreta en un archivo:

```

mcdanymx@kali:~/picoCTF/whatlieswithin

 $ ls

amcdanymx@kali:~/picoCTF/whatlieswithin

 $ wget https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png

--2022-10-10 18:07:23--  https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png

Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8

Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.

Petición HTTP enviada, esperando respuesta... 200 OK

Longitud: 625219 (611K) [application/octet-stream]

Grabando a: «buildings.png»

  

buildings.png            100%[==============================================>] 610.57K  1.48MB/s en 0.4s    

  

2022-10-10 18:07:24 (1.48 MB/s) - «buildings.png» guardado [625219/625219]

  

amcdanymx@kali:~/picoCTF/whatlieswithin

 $ ls

buildings.png

amcdanymx@kali:~/picoCTF/whatlieswithin

 $ open buildings.png

  
**


```

Podemos utilizar un decodificador online como **https://stylesuxx.github.io/steganography/** para decodificar la imagen y encontrar la información en este caso la bandera:

```
picoCTF{h1d1ng_1n_th3_b1t5}

```


