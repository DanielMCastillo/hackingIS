# USERNAME picoCTF -> amcdanymx
# What's a net car

## Description

Usar netcat (nc) va a ser bastante importante. ¿Puede conectarse a jupiter.challenges.picoctf.org en el puerto 25103 para obtener la bandera?

## Pista
nc [tutorial](https://linux.die.net/man/1/nc)

## Soución

Al mirar la sugerencia y hacer clic en la palabra tutorial, somos redirigidos a la página del manual de netcat de Linux. El nc (o netcat) se usa para abrir conexiones TCP, enviar paquetes UDP, escuchar conexiones UDP y TCP en los puertos respectivos. También se usa para escanear puertos, entre otras cosas.

El comando completo que usé:

```
netcat jupiter.challenges.picoctf.org 25103
You're on your way to becoming the net cat master
picoCTF{nEtCat_Mast3ry_d0c64587}
```