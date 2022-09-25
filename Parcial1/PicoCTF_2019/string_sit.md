# USERNAME picoCTF -> amcdanymx

# String Sit

## Description
¿Puedes encontrar el indicador en el archivo sin ejecutarlo?


## Pista
[strings](https://linux.die.net/man/1/strings)

## Soución

Para resolver este desafío, primero hice clic en la palabra del archivo en la descripción. Al hacer clic, se descargó un archivo. El archivo se llama strings.

Después de leer el manual, decidí ejecutar el comando "strings strings", que es básicamente el comando strings en el archivo strings. Este comando devolvió una enorme cantidad de cadenas, lo que dificultaba demasiado encontrar la bandera.

Ppara resolver este desafío use loc omandos pipe y grep de la terminal de Linux, así:

- Descargué el archivo
- cd /Descargas

```
strings strings | grep pico 
picoCTF{5tRIng5_1T_d66c7bb7}
```