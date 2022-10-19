# USERNAME -> amcdanymx



## Description

This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/50522/` ([link](https://jupiter.challenges.picoctf.org/problem/50522/)) or http://jupiter.challenges.picoctf.org:50522

*Pista*
You don't need to download a new web browser

* cuando abrimos el link nos abre una página, pero nos dice un error
![[Pasted image 20220924132202.png]]
*You're not picobrowser! Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/104.0.5112.102 Safari/537.36 OPR/90.0.4480.100*

El navegador se identifica como que no es picobrowser

* Vamos a inspeccionar elemento y buscamos la flag, vemos que en la parte de user agent aparece una versión de nuestro navegador
* Hay que cambiar el user agent
![[Pasted image 20220924132442.png]]

Modificamos la solicitud y la cambiamos por
*picobrowser*
![[Pasted image 20220924133118.png]]

- Selecciono la petición y veo la respuesta con el nuevo header value
- ![[Pasted image 20220924133433.png]]

Conseguimos la bandera:

```
picoCTF{p1c0_s3cr3t_ag3nt_51414fa7}
```
