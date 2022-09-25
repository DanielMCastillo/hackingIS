# USERNAME picoCTF -> amcdanymx

# Plumbing

## Description
A veces necesita manejar datos de proceso fuera de un archivo. ¿Puedes encontrar una manera de mantener la salida de este programa y buscar la bandera? Conéctese a jupiter.challenges.picoctf.org 14291.

## Pistas

- Recuerda que el formato de la bandera es picoCTF{XXXX}
- ¿Qué es una pipa? No, no ese tipo de pipa... Este tipo [kind](http://www.linfo.org/pipes.html)

## Soución

Nos conectamos al puerto esécificado con el siguiente comando, ya sabemos que tenemos que usar nc
Nos sale un ciclo de texto el cual  podemos usar una pipe |. Lo que hace en Shell es que nos permite combinar dos comandos en uno. Entonces, si quisiéramos grep el valor de retorno de la conexión del host netcat para un indicador, podemos ejecutar nc
```
nc jupiter.challenges.picoctf.org 14291
flag either
Not a flag either 
Not a flag either 
Not a flag either 
Not a flag either Not a flag either Not a flag either Again, I really don't think this is a flag Not a flag either Again, I really don't think this is a flag Not a flag either Not a flag either Not a flag either Not a flag either I don't think this is a flag either Not a flag either Again, I really don't think this is a flag This is defintely not a flag Again, I really don't think this is a flag Again, I really don't think this is a flag Not a flag either This is defintely not a flag Not a flag either Again, I really don't think this is a flag Not a flag either
```

```
nc jupiter.challenges.picoctf.org 14291 | grep picoCTF
picoCTF{digital_plumb3r_ea8bfec7}

```