# USERNAME -> amcdanymx


#### Description

Can you get the flag?Download this [binary](https://artifacts.picoctf.net/c/117/gdbme).Here's the test drive instructions:

-   `$ chmod +x gdbme`
-   `$ gdb gdbme`
-   `(gdb) layout asm`
-   `(gdb) break *(main+99)`
-   `(gdb) run`
-   `(gdb) jump *(main+104)`

#### PISTAS
- (None)
-
#### SOLUCIÓN

En este reto ocupamos una herramienta llamada gdb, la cual se tiene que instalar, procedemos a descargar el archivo que nos brinda el reto y ejectuamos con gdb, se nos abre una consola nueva y ahí introduciremos los comandos que nos dan en la descripción:

```
amcdanymx:gdbtestdrive/ $ gdb gdbme                                     

GNU gdb (Debian 12.1-4) 12.1

Copyright (C) 2022 Free Software Foundation, Inc.

License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>

This is free software: you are free to change and redistribute it.

There is NO WARRANTY, to the extent permitted by law.

Type "show copying" and "show warranty" for details.

This GDB was configured as "x86_64-linux-gnu".

Type "show configuration" for configuration details.

For bug reporting instructions, please see:

<https://www.gnu.org/software/gdb/bugs/>.

Find the GDB manual and other documentation resources online at:

<http://www.gnu.org/software/gdb/documentation/>.

  

For help, type "help".

Type "apropos word" to search for commands related to "word"...

Reading symbols from gdbme...

(No debugging symbols found in gdbme)

(gdb) layout asm

```

Consola GDB
```
-   $ chmod +x gdbme
    
-   $ gdb gdbme
    
-   (gdb) layout asm
    
-   (gdb) break *(main+99)
    
-   (gdb) run
    
-   (gdb) jump *(main+104)
    

picoCTF{d3bugg3r_dr1v3_7776d758}

```

Obtenemos la bandera: picoCTF{d3bugg3r_dr1v3_7776d758}