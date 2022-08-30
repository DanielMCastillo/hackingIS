# BANDIT LEVEL 9 -> LEVEL 10

# Objetivo

The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd



# Datos de acceso

USERNAME: **bandit9**
PASSWORD:  truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

# Solución

- Usamos ls para listar los archivos, encontramos el archivo data.txt
- Filtramos con `grep` - grep  '=' data.txt pero no podemos leerlo
-  Por lo tanto, usamos el comando `strings`, quien nos imprime las cadenas de caracteres `imprimibles` en un archivo. El output de este comando lo redireccionamos a un `grep`, para buscar por varios: '=' 
- `strings data.txt | grep '='`


# Notas adicionales


