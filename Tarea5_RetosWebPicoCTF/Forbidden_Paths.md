# USERNAME -> amcdanymx

# Forbidden Paths


## Description
Can you get the flag?Here's the [website](http://saturn.picoctf.net:55827/).We know that the website files live in `/usr/share/nginx/html/` and the flag is at `/flag.txt` but the website is filtering absolute file paths. Can you get past the filter to read the flag?

## Pistas

- (None)

## Solución

En este reto basicamente tenemos que insperccionar el sitio nuevamente, ahora nos dice que hay que filtrar por las rutas de los archivos para encontrar la bandera, intente ingresando al archivo con ruta /flag.txt pero me salió un error:
```
Not Authorized

```

En el campo del sitio web lo que hice fue moverme entre las rutas para al final ingresar de la siguiente manera moviendome hasta la raíz

```
../../../../../flag.txt

```

```
picoCTF{7h3_p47h_70_5ucc355_e5a6fcbc}
```