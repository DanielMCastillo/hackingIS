# USERNAME picoCTF -> amcdanymx

# PW Crack 2

## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/18/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/18/level2.flag.txt.enc) in the same directory too.

## Pistas
Does that encoding look familiar?
The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución 
Descargamos los dos archivos, y analizamo el código de python
```
(amcdanymx@kali)-[~/Descargas]

└─$ cat level2.py   

### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################

def str_xor(secret, key):

#extend key to secret length

new_key = key

i = 0

while len(new_key) < len(secret):

     new_key = new_key + key[i]

     i = (i + 1) % len(key)    

return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])

###############################################################################

  

flag_enc = open('level2.flag.txt.enc', 'rb').read()


def level_2_pw_check():

user_pw = input("Please enter correct password for flag: ")

if( user_pw == chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65) ):

     print("Welcome back... your flag, user:")

     decryption = str_xor(flag_enc.decode(), user_pw)

     print(decryption)

     return

print("That password is incorrect")

level_2_pw_check()


```

Vemos que la contraseña está como encriptada en forma de caracteres Ascii, usamos lo mismo que en desafíos pasados donde con el mismo python la imprimimos ya que python3 especificamente imprime en forma de texto estos dígitos:


```
                                                                          ┌──(amcdanymx㉿kali)-[~/Descargas]

└─$ python3     

Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux

Type "help", "copyright", "credits" or "license" for more information.

>>> print(chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65))

39ce

>>> exit()**


```

Ya tenemos la contraseña, ahora ejecutamos el archivo y cuando nos pida la contraseña la introducimos 

```

┌──(amcdanymx@kali)-[~/Descargas]

└─$ python3 level2.py

Please enter correct password for flag: 39ce

Welcome back... your flag, user:

picoCTF{tr45h_51ng1ng_502ec42e}


```