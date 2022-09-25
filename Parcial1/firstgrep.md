# USERNAME picoCTF -> amcdanymx

# First grep

## Description
¿Puedes encontrar la bandera en el file? Esto sería muy tedioso de revisar manualmente, algo me dice que hay una mejor manera.


## Pista
grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)

## Solución

Usamos el comando grep como se muestra en el tutorial, al darle click en el archivo que nos dan se nos descarga uno llamado "file"

usamos el siguiente comando para leer el archivo y conocer la bandera:


```
cat file | grep picoCTF
picoCTF{grep_is_good_to_find_things_f77e0797}

```
