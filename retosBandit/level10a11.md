# BANDIT LEVEL 10 -> LEVEL 11

# Objetivo

The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd



# Datos de acceso

USERNAME: **bandit10**
PASSWORD:  IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

# Solución

- Usamos ls para listar los archivos
- Usamos el comando `cat` + nombre de archivo 
- recibimos una cadena en base diferente  
- Podemos especificar la codificación de la cadena en su base, usamos base 64 por lo tanto el comando nos queda así: `cat data.txt | base64 -d`


# Notas adicionales


