# USERNAME -> amcdanymx

#### Description

In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/d31ce4356bdfd15d33a9af7e35ab4d0a/VaultDoor5.java)


#### PISTAS
- You may find an encoder/decoder tool helpful, such as https://encoding.tools/
- Read the wikipedia articles on URL encoding and base 64 encoding to understand how they work and what the results look like.


#### SOLUCIÓN

Desccargamos el larchivo que nos proporcionan llamado VaultDoor5.java, nuevamente un código de java donde el usuario introduce la password y dice si puede entrar o no, al explorar  vemos que hay cadenas que estan codificadas en base64, lo tenemos que decodificar al contrario, hacerle base64 y luego la url decode, en este caso usamos una herramienta online:

https://gchq.github.io/CyberChef/

```
JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVmJTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2JTM0JTVmJTY1JTMzJTMxJTM1JTMyJTYyJTY2JTM0
```
  

Obtenemos la decodificación:
```
c0nv3rt1ng_fr0m_ba5e_64_e3152bf4
```