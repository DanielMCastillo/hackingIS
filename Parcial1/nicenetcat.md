# USERNAME picoCTF -> amcdanymx


# Nice netcat

## Desafío

Hay un buen programa con el que puedes hablar usando este comando en un shell: $ nc mercury.picoctf.net 49039, pero no habla inglés...

## Pista

Puedes practicar el uso de netcat con este problema de picoGym:  [what's a netcat?](https://play.picoctf.org/practice/challenge/34)
Puedes practicar la lectura y escritura ASCII con este problema de picoGym:[Let's Warm Up](https://play.picoctf.org/practice/challenge/22)


## Solución
Empezamos introduciendo el comando que se nos da para conectarnos en el shell

```
 nc mercury.picoctf.net 49039
 112 105 99 111 67 84 70 123 103 48 48 100 95 107 49 116 116 121 33 95 110 49 99 51 95 107 49 116 116 121 33 95 51 100 56 52 101 100 99 56 125 10
 
```

Nos da una lista de numeros decimales, lo vamos a convertir a Ascii, para ello usamos herramientas como esta:
https://www.rapidtables.com/convert/number/ascii-hex-bin-dec-converter.html

Al convertirlo nos queda que la bandera es:
```
picoCTF{g00d_K1tty!_n1c3_k1tty!_3d84edc8}

```
