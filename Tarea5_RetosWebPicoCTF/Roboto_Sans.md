# USERNAME -> amcdanymx

# Roboto Sans

## Description

The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:64710/) out.

## Pistas

- (None)

## Solución

Ingresamos al sitio web, como nos mecniona el nombre del reto podemos suponer que tiene que ver con el archivo de robots, lo buscamos 


```

*http://saturn.picoctf.net:64710/robots.txt* 

User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/

```

Vemos que nos aparece un tipo de código es un tipo de seguridad, lo que haremos será ir a una página llamada cyberchef, ponemos que nos convierta la parte de la cadena que asigna la codificación desde Base64, nos muestra lo siguiente:

```
js/myfile.txt

```

Vemos la ruta de ese archivo que aparecía oculto, ingresamosal archivo
```
http://saturn.picoctf.net:64710/js/myfile.txt
```

Y encontramos la bandera:
```
picoCTF{Who_D03sN7_L1k5_90B0T5_032f1c2b}
```
