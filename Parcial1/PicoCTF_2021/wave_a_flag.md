# USERNAME picoCTF -> amcdanymx

# Wave a Flag

## Description
¿Puede invocar banderas de ayuda para una herramienta o binario? Este programa tiene información extraordinariamente útil...

## Pistas

Este programa solo funcionará en webshell u otra computadora con Linux.

Para acceder al archivo en su shell, ingrese lo siguiente en el indicador de Terminal: $ wget https://mercury.picoctf.net/static/fc1d77192c544314efece5dd309092e3/warm

Ejecute este programa ingresando lo siguiente en el indicador de la Terminal: $ ./warm, pero primero tendrá que hacerlo ejecutable con $ chmod +x warm

-h y --help son los argumentos más comunes que se dan a los programas para obtener más información de ellos.

No todos los programas implementan funciones de ayuda como -h y --help.


## Solución
Abrimos la terminal, descargamos el archivo que se nos da en la liga, es un ejecutable llamado "warm"

```

file warm
warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=7b3da2efd83a2b9154697b6c7f6474042e1fd033, with debug_info, not stripped
```
intentamos ejecutar el archivo 
```
./warm

zsh:permiso denegado ./warm

```

me sale un error que no tengo permisos, lo único que hice fue cambiar los permisos

```
chmod 777 warm
```

Ahora si lo volvemos a ejcutar
```
./warm
Hello user! Pass me a -h to learn what I can do!

```

Le pasamos la instruccion -h como nos dice
```
./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_6635aa47}
```