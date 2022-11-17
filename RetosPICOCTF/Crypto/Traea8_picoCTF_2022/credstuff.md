# USERNAME -> amcdanymx

#### Description

We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it?Download the leak [here](https://artifacts.picoctf.net/c/534/leak.tar).The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.


#### PISTAS

- Maybe other passwords will have hints about the leak?

#### SOLUCIÓN
En este reto nos dan dos archiivos uno con passwords y otro con usuarios, si buscamos el usuario con el nombre  cultiris, vemos que se ecientra en la linea 378, mapeamos esa linea a las contraseñas, analizando vemos que tiene un encriptado ceasar, utilizarmoe una herramienta para desencriptar, yo encontré esta https://www.dcode.fr/caesar-cipher
 copiamos el codigo sin desencriptar y nos da la bandera:

```
Codigo encriptado:
cvpbPGS{P7e1S_54I35_71Z3}

Desencriptado y bandera:
picoCTF{C7r1F_54V35_71M3}

```
