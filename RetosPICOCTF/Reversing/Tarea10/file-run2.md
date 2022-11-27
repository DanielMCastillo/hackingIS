# USERNAME -> amcdanymx

#### Description

Another program, but this time, it seems to want some input. What happens if you try to run it on the command line with input "Hello!"?Download the program [here](https://artifacts.picoctf.net/c/353/run).
  
#### PISTAS
- Try running it and add the phrase "Hello!" with a space in front (i.e. "./run Hello!")

#### SOLUCIÓN


```
amcdanymx:filerun2/ $ ls                                               
run

amcdanymx:filerun2/ $ ./run                                             

zsh: permiso denegado: ./run

amcdanymx:filerun2/ $ file run                                          

run: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=e923d195967f2f793c6de52cee78b8fb7f3c0a2a, for GNU/Linux 3.2.0, not stripped

amcdanymx:filerun2/ $ ./run test                                        

zsh: permiso denegado: ./run

amcdanymx:filerun2/ $ ls -l                                             
total 20
-rw-r--r-- 1 amcdanymx amcdanymx 16816 mar 15  2022 run
amcdanymx:filerun2/ $ chmod 777 run                                     

amcdanymx:filerun2/ $ ./run                                             
Run this file with only one argument.

amcdanymx:filerun2/ $ ./run test                                        

Won't you say 'Hello!' to me first?

amcdanymx:filerun2/ $ ./run Hello!                                      

The flag is: picoCTF{F1r57_4rgum3n7_f65ed63e}%                         
**
```

Y obtenemos la bandera: picoCTF{F1r57_4rgum3n7_f65ed63e}