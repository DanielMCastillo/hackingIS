# USERNAME picoCTF -> amcdanymx

# Codebook

## Descripción

#### Description

Run the Python script `code.py` in the same directory as `codebook.txt`.

-   [Download code.py](https://artifacts.picoctf.net/c/102/code.py)
-   [Download codebook.txt](https://artifacts.picoctf.net/c/102/codebook.txt)

## Pistas

En el shell web, use ls para ver si ambos archivos están en el directorio en el que se encuentra
La función str_xor no necesita ingeniería inversa para este desafío.

## Solución 

- Descargamos ambos archivos
- Vemos que esten en el mismo directorio
- Ejectuamos con python

```

┌──(amcdanymx@kali)-[~/Descargas]

└─$ ls

Addadshashanammu              codebook.txt  runme.py

Addadshashanammu.zip          code.py

code_1.71.2-1663191218_amd64.deb  convertme.py

┌──(amcdanymx@kali)-[~/Descargas]

└─$ python code.py  

picoCTF{c0d3b00k_455157_197a982c}

```
