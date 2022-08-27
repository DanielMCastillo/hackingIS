# BANDIT LEVEL 8 -> LEVEL 9

# Objetivo

The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

## Comandos útiles

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd



# Datos de acceso

DATOS DE ACCESO

USERNAME: **bandit8**
PASSWORD:  UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

# Solución

Para buscar líneas únicas en un archivo usamos el comando uniq con la opción '-u'

uniq -u data.txt


Se nos presenta el primer problema, que es el desorden del texto. Para encontrar la solución, ordenamos el contenido del archivo usando con  'sort'

sort data.txt 

Ahora que el texto se encuentra ordenado, podemos redireccionar la salida del comando sort al comando uniq -u a través del símbolo |

sort data.txt | uniq -u


# Notas adicionales


