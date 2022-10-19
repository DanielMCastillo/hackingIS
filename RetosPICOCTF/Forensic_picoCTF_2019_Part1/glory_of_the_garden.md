# USERNAME -> amcdanymx

## Glory of the garden

#### Description

This [garden](https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg) contains more than it seems.

  
#### PISTAS

What is a hex editor?


#### SOLUCIÓN

Descargamos el archivo que se nos da en el enalce, el cual contiene un archivo con extensión .jpg “garden.jpg”

Podemos ver el contenido del archivo con:
```open garden.jpg```


Podemos ver el contenido hexadecimal de un archivo con el comando:

```xxd garden.jpg```

EL reto trata sobre averiguar que es un editor hexadeximal, podemos entrar a uno de estos editores con el comando 
```hexeditor garden.jpg```

Dentro del editor se nos permite edirar el archivo de forma haxadecimal.

``` 
File: garden.jpg                              ASCII Offset: 0x00000000 / 0x00230597 (%00)   

00000000  FF D8 FF E0  00 10 4A 46   49 46 00 01  01 01 00 48               ......JFIF.....H

00000010  00 48 00 00  FF E2 0C 58   49 43 43 5F  50 52 4F 46               .H.....XICC_PROF

00000020  49 4C 45 00  01 01 00 00   0C 48 4C 69  6E 6F 02 10               ILE......HLino..

00000030  00 00 6D 6E  74 72 52 47   42 20 58 59  5A 20 07 CE               ..mntrRGB XYZ ..

00000040  00 02 00 09  00 06 00 31   00 00 61 63  73 70 4D 53               .......1..acspMS

00000050  46 54 00 00  00 00 49 45   43 20 73 52  47 42 00 00               FT....IEC sRGB..

00000060  00 00 00 00  00 00 00 00   00 00 00 00  F6 D6 00 01               ................

00000070  00 00 00 00  D3 2D 48 50   20 20 00 00  00 00 00 00               .....-HP  ......

00000080  00 00 00 00  00 00 00 00   00 00 00 00  00 00 00 00               ................

```


Podemos filtrar con la opción de contrl + w, buscamos con la opción de “find text” o “search for text string”,

Usando esta opción podemos buscar “picoCTF” para encontrar la bandera

```
File: garden.jpg                              ASCII Offset: 0x0023056E / 0x00230597 (%100)  

00230560  72 65 20 69  73 20 61 20   66 6C 61 67  20 22 70 69               re is a flag "pi

00230570  63 6F 43 54  46 7B 6D 6F   72 65 5F 74  68 61 6E 5F               coCTF{more_than_

00230580  6D 33 33 74  73 5F 74 68   65 5F 33 79  33 65 42 64               m33ts_the_3y3eBd

00230590  42 64 32 63  63 7D 22 0A                                          Bd2cc}".

```
La bandera es: 
```picoCTF{more_than_m33ts_the_3y3eBdBd2cc}```