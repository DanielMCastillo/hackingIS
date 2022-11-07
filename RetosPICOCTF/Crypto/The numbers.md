# USERNAME -> amcdanymx

#### Description

Download this image file and find the flag.

-   [Download image file](https://artifacts.picoctf.net/c/138/drawing.flag.svg)


#### PISTAS
No hay 


#### SOLUCIÓN
Descargamos el archivo, es un archivo de imagen, procedemos  aabrirlo, vemos que el archivo contiene una imagen con numeros en estructura de la bandera del desafio, la bandera que podemos ver es:


16 9 3 15 3 20 6 {20 8 5 14 21 13 2 5 18 19 13 1 19 15 14}


```
picoCTF/thenumbers [ wget https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png   

--2022-11-07 13:53:40--  https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png

Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8

Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.

Petición HTTP enviada, esperando respuesta... 200 OK

Longitud: 100721 (98K) [application/octet-stream]

Grabando a: «the_numbers.png»

  

the_numbers.png          100%[==============================================>]  98.36K  --.-KB/s en 0.1s    

  

2022-11-07 13:53:41 (919 KB/s) - «the_numbers.png» guardado [100721/100721]

  

picoCTF/thenumbers [ ls                                                                                 ] 1:53

the_numbers.png

picoCTF/thenumbers [ open the_numbers.png                               
```

Deciframos la bandera, sabemos que contiene numerros, yo intuí que era una codificación, lo cual llegué a la conlución de que era código ASCII, decidí decifrarlo a mano, cada numero en la tabla ASCII corresponde a un elemento de la bandera, la cual es:

```
**

picoCTF{thenumbersmason}

**

```
