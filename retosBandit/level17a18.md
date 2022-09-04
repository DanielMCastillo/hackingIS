# BANDIT LEVEL 17 -> LEVEL 18

# Objetivo

## Level Goal

There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**

## Commands you may need to solve this level

cat, grep, ls, diff


# Datos de acceso

USERNAME: **bandit17**
PASSWORD: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

# Solución
Revisamos y listamos los archivos

- ls

Vemos que tenemos dos archivos uno llamado 
passwords.old y password.new, donde la contraseña se encuentra entre una línea que ha cambiado entre los dos archivos.

podemos usar el comando diff para encontrar la línea que es diferente y encontrar la contraseña.

- diff password.old passwords.new 

si queremos agregar colores podemos agregar la instruccion --color


- diff password.old passwords.new --color

# Notas adicionales


