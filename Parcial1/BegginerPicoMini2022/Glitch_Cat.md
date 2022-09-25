# USERNAME picoCTF -> amcdanymx

# fixme2.py


## Descripción

#### Description

Our flag printing service has started glitching!`$ nc saturn.picoctf.net 51109`


## Pistas
- ASCII is one of the most common encodings used in programming
- We know that the glitch output is valid Python, somehow!
- Press Ctrl and c on your keyboard to close your connection and return to the command prompt.

## Solución 

Si ejectuamos  solo desde consola nos da caracteres en codigo Ascii, pero si ejecutamos desde la cojnsola python más especificamente con Python3 este lenguaje se encarga de imprimir dichos caracteres de forma normal, la salida es:


```

──(amcdanymx@kali)-[~/Descargas]

└─$ nc saturn.picoctf.net 51109                       

'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'

┌──(amcdanymx@kali)-[~/Descargas]

└─$ python3     

Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux

Type "help", "copyright", "credits" or "license" for more information.

>>> print('picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}')

picoCTF{gl17ch_m3_n07_bda68f75}

  
```

