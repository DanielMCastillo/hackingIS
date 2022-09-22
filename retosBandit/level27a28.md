# Level 26 -> 27 

## Objetivo

-   There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.

## Commands you may need to solve this level

git

## Datos de acceso

-   Host: bandit.labs.overthewire.org
-   Port: 2220
-   User: bandit27
-   Password: AVanL161y9rsbcJIsFHuw35rjaOM19nR

## Solución


Clonamos el repositorio en local

```
git clone ssh://bandit27-git@localhost/home/bandit27-git/repo
```

Y justamente en el archivo README del repositorio encontramos la contraseña.

```
cat repo/README
AVanL161y9rsbcJIsFHuw35rjaOM19nR
```

## Notas adicionales
