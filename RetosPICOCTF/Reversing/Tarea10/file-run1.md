# USERNAME -> amcdanymx


#### Description

A program has been provided to you, what happens if you try to run it on the command line?Download the program [here](https://artifacts.picoctf.net/c/310/run).
  
#### PISTAS
- To run the program at all, you must make it executable (i.e. `$ chmod +x run`)
- Try running it by adding a '.' in front of the path to the file (i.e. `$ ./run`)

#### SOLUCIÓN

Descargamos el archivo que se nos da mediante el enlace, intenté ejecutar el archivo pero no se pudo, no teníamos los permisos necesarios, simplemente se tiene que cambiar los permisos al archivo con el comando chmod, y lo intentamos ejecturar nuevamente.

```
amcdanymx:filerun1/ $ ls                                                
run

amcdanymx:filerun1/ $ file run                                          

run: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=0514683255a9ef58abe3c729e7418d07210a759e, for GNU/Linux 3.2.0, not stripped

amcdanymx:filerun1/ $ ls -l                                             
total 20
-rw-r--r-- 1 amcdanymx amcdanymx 16736 mar 15  2022 run
amcdanymx:filerun1/ $ chmod 777 run                                     
amcdanymx:filerun1/ $ ./run                                                      
The flag is: picoCTF{U51N6_Y0Ur_F1r57_F113_47cf2b7b}%
```

Y obtenemos la bandera:  picoCTF{U51N6_Y0Ur_F1r57_F113_47cf2b7b}