# Level 30 ->31

# Objetivo

-   Hay un repositorio en `ssh://bandit30git@localhost:2220/home/bandit30-git/repo`. La contraseña para el usuario `bandit30-git` es la misma para el usuario `bandit30`.

Clonamos el repostorito y podramos avanzar al otro nivel
Datos de acceso

-   Host: bandit.labs.overthewire.org
-   Port: 2220
-   User: bandit30
-   Password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

## Solución

-   Al leer el archivo README, encontrará que está "vacío", al navegar a través de confirmaciones y ramas no encontrará nada. Intente mirar las etiquetas con "git tag".

```
bandit30@bandit:/tmp/rep30$ ls
repo
bandit30@bandit:/tmp/rep30$ cd repo
bandit30@bandit:/tmp/rep30/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/rep30/repo$ git log
commit a325f29e1cc26b0f0dc5f89b4348e389b408cc87 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:28 2022 +0000

    initial commit of README.md
bandit30@bandit:/tmp/rep30/repo$ git tag
secret
bandit30@bandit:/tmp/rep30/repo$ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
bandit30@bandit:/tmp/rep30/repo$
```

## Notas adicionales
