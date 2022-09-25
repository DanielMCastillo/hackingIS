# USERNAME picoCTF -> amcdanymx

# Codebook

## Descripción


Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/39/fixme1.py)

## Pistas

- Indentation is very meaningful in Python
- To view the file in the webshell, do: `$ nano fixme1.py`
- To exit `nano`, press Ctrl and x and follow the on-screen prompts.
- The `str_xor` function does not need to be reverse engineered for this challenge.


## Solución 

Descargamos el archivo de python, al ejecutar nos sale un errror

```

┌──(amcdanymx@kali)-[~/Descargas]

└─$ python fixme1.py

  File "/home/amcdanymx/Descargas/fixme1.py", line 20

print('That is correct! Here\'s your flag: ' + flag)

IndentationError: unexpected indent
```

Vemos el código de python
```
import random

def str_xor(secret, key):

    #extend key to secret length

    new_key = key

    i = 0

    while len(new_key) < len(secret):

        new_key = new_key + key[i]

        i = (i + 1) % len(key)        

    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])



flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5a) + chr(0x07) + chr(0x00) + chr(0x46) + chr(0x0b) + chr(0x1a) + chr(0x5a) + chr(0x1d) + chr(0x1d) + chr(0x2a) + chr(0x06) + chr(0x1c) + chr(0x5a) + chr(0x5c) + chr(0x55) + chr(0x40) + chr(0x3a) + chr(0x5f) + chr(0x53) + chr(0x5b) + chr(0x57) + chr(0x41) + chr(0x57) + chr(0x08) + chr(0x5c) + chr(0x14)

  
flag = str_xor(flag_enc, 'enkidu')
  print('That is correct! Here\'s your flag: ' + flag)
```

Corregimos un error que había en la identación al imprimir en la última línea ¿
Nos queda así
```

┌──(amcdanymx@kali)-[~/Descargas]

└─$ python fixme1.py

  File "/home/amcdanymx/Descargas/fixme1.py", line 20

print('That is correct! Here\'s your flag: ' + flag)

IndentationError: unexpected indent
```

Vemos el código de python
```
import random

def str_xor(secret, key):

    #extend key to secret length

    new_key = key

    i = 0

    while len(new_key) < len(secret):

        new_key = new_key + key[i]

        i = (i + 1) % len(key)        

    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])



flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5a) + chr(0x07) + chr(0x00) + chr(0x46) + chr(0x0b) + chr(0x1a) + chr(0x5a) + chr(0x1d) + chr(0x1d) + chr(0x2a) + chr(0x06) + chr(0x1c) + chr(0x5a) + chr(0x5c) + chr(0x55) + chr(0x40) + chr(0x3a) + chr(0x5f) + chr(0x53) + chr(0x5b) + chr(0x57) + chr(0x41) + chr(0x57) + chr(0x08) + chr(0x5c) + chr(0x14)

  
flag = str_xor(flag_enc, 'enkidu')
print('That is correct! Here\'s your flag: ' + flag)
```

Guardamos y volvemos a ejecutar
```

┌──(amcdanymx㉿kali)-[~/Descargas]

└─$ python fixme1.py

That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}

```

Nos dan la bandera. 