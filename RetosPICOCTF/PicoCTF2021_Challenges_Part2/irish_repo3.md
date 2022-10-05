# USERNAME -> amcdanymx

# Irish Repo 3


## Description

There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/40742/` ([link](https://jupiter.challenges.picoctf.org/problem/40742/)) or http://jupiter.challenges.picoctf.org:40742. Try to see if you can login as admin!

## Pistas
- Seems like the password is encrypted.

## Solución
Entramos al link que se nos proporciona, al entrar al sitio vemos que ahora es diferente a los otros dos sitios anteriores de los challenges de irish, en esta ocasión solo tenemos el campo para la contraseña

Inspeccionamos el código
Vemos que tenemos el modo de debug en 0, ahora lo cambiamos nuevamente a 1
Nos aparece lo siguiente al intentarlo nuevamente


```
password: holamundo
SQL query: SELECT * FROM admin where password = 'ubynzhaqb'

# Login failed.

```

Utilizamos la erramienta de CyberChef para decodificar la password en ROT13, ingresamos la contraseña que se nos da y la cambiamos:

```
picoCTF{3v3n_m0r3_SQL_4424e7af}


```