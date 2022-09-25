# USERNAME picoCTF -> amcdanymx


# PW Crack 1

## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/52/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/52/level1.flag.txt.enc) in the same directory too.

## Pistas
To view the file in the webshell, do: `$ nano level1.py`
To exit `nano`, press Ctrl and x and follow the on-screen prompts.
The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución 

Descargar los archivos en el mismo directorio. Analizamos el script de python y podemos ver que la contraseña está en un if casi al final
Ejecutamos primero en consola para leer el archivo y ver que contiene, también se puede hacer desde un editor de texto

```
┌──(amcdanymx@kali)-[~/Descargas]

└─$ cat level1.py

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

  
  

flag_enc = open('level1.flag.txt.enc', 'rb').read()

  
  
  

def level_1_pw_check():

user_pw = input("Please enter correct password for flag: ")

if( user_pw == "1e1a"):

     print("Welcome back... your flag, user:")

     decryption = str_xor(flag_enc.decode(), user_pw)

     print(decryption)

     return

print("That password is incorrect")

  

level_1_pw_check()

```

Vemos la contraseña en el if ahora ejecutamos el archivo  y cuando nos lo pida introducimos la contraseña correcta, tenemos la bandera.
```
┌──(amcdanymx@kali)-[~/Descargas]

└─$ python level1.py

Please enter correct password for flag: 1e1a

Welcome back... your flag, user:

picoCTF{545h_r1ng1ng_fa343060}


```