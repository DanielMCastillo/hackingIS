# USERNAME picoCTF -> amcdanymx

# Based

## Description
Para obtener realmente 1337, debe comprender diferentes codificaciones de datos, como hexadecimal o binario. ¿Puedes obtener la bandera de este programa para demostrar que estás en camino de convertirte en 1337? Conéctese con nc jupiter.challenges.picoctf.org 15130.

## Pista
Escuché que Python puede convertir cosas
Puede ser útil tener varias ventanas abiertas.

## Soución
Lo primero que tenemos que hacer es correr un comando para poder obtener la bandera
usamos nuevamente nc, al ingresarlo nos sale como un minichallenge donde tenemos que hacer las respectivas conversiones, yo me percaté que primero era un numero binario convertirlo a texto, después era un Octal a texto y finalmente un hexadecimal a texto.


Para las conversiones hice uso de paginas online para convertirlos
https://www.rapidtables.com/convert/number/decimal-to-binary.html
```

nc jupiter.challenges.picoctf.org 15130 
Let us see how data is stored lime Please give the 01101100 01101001 01101101 01100101 as a word. ... you have 45 seconds..... 
Input: lime
Please give me the 143 157 156 164 141 151 156 145 162 as a word. 
Input: container 
Please give me the 7461626c65 as a word. 
Input: table You've beaten the challenge Flag: picoCTF{learning_about_converting_values_02167de8}
```