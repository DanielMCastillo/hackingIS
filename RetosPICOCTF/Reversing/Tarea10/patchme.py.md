# USERNAME -> amcdanymx

#### Description

Can you get the flag?Run this [Python program](https://artifacts.picoctf.net/c/388/patchme.flag.py) in the same directory as this [encrypted flag](https://artifacts.picoctf.net/c/388/flag.txt.enc).

#### PISTAS
- None

#### SOLUCIÓN

Descargamos el archivo que se nos da mediante el enlace, este archivo tiene extensión .py lo que sabemos que es un archivo python, también nos danuna archivo con la bandera encriptada, dicho archivo se pasa como parametro en el código python

En el código nos encontramos con una función que se ejecuta al final, dicha función contiene un if donde lo que se ingresa debe ser igual a lo que está en el if para que nos de la bandera, simplemente comenté el if y volví a ejecutar ya que no es necesario.
```  
def level_1_pw_check():

   user_pw = input("Please enter correct password for flag: ")

   #if( user_pw == "ak98" + \

                  #"-=90" + \

                  #"adfjhgj321" + \

                  #"sleuth9000"):

   print("Welcome back... your flag, user:")

   decryption = str_xor(flag_enc.decode(), "utilitarian")

   print(decryption)

   return

   print("That password is incorrect")

level_1_pw_check()

```

Ejecutamos el código junto con la flag encriptada y aunqeu pongamos cualquier cadena nos dará la respuesta:

```
mcdanymx:patchme/ $ ls                                                

flag.txt.enc  patchme.flag.py

amcdanymx:patchme/ $ code patchme.flag.py                              
amcdanymx:patchme/ $ ls                                                 

flag.txt.enc  patchme.flag.py

amcdanymx:patchme/ $  python patchme.flag.py ./flag.txt.enc             
Please enter correct password for flag: ak98

That password is incorrect
```

Volvemos a ejecutar el archivo:

```
amcdanymx:patchme/ $  python patchme.flag.py ./flag.txt.enc             

Please enter correct password for flag: hola

Welcome back... your flag, user:

picoCTF{p47ch1ng_l1f3_h4ck_21d62e33}

```

y obtenemos la bandera: picoCTF{p47ch1ng_l1f3_h4ck_21d62e33}
