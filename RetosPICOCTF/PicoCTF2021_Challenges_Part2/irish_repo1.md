# USERNAME -> amcdanymx

# Irish Repo 1


## Description

There is a website running at `https://jupiter.challenges.picoctf.org/problem/50009/` ([link](https://jupiter.challenges.picoctf.org/problem/50009/)) or http://jupiter.challenges.picoctf.org:50009. Do you think you can log us in? Try to see if you can login!


## Pistas
- There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?
- Try to think about how the website verifies your login.


## Solución

Entramos a la página que se nos proporciona, en mi caso entré usando el link, inspeccionando vemos que hay un login, hay inicio de sesión de administrador, si ingreso alguna credencial solo por probar no nos deja ingresar, lo que probaremos es SQli.

Probemos un Basic payload que es:

*admin'or'1'='1 --*

Conseguimos la bandera:

```
picoCTF{s0m3_SQL_fb3fe2ad}

```
