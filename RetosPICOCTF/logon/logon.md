## Description

The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/15796/` ([link](https://jupiter.challenges.picoctf.org/problem/15796/)) or http://jupiter.challenges.picoctf.org:15796


Se muestra ina página de login al seguir el link 

![[Pasted image 20220924125057.png]]

En el username ponemos "Joe" y en el password ponemos cualquiera "HolaMundo"

![[Pasted image 20220924125152.png]]

Nos da un tipo de error que nos menciona que el usuario Joe solo se está validando para este usuario, intentaremos entrar como otro usuario 

![[Pasted image 20220924125238.png]]
Si usamos otro usuario y ententamos entrar vemoos que esta vez no nos da ese error

"Success: You logged in! Not sure you'll be able to see the flag though."
![[Pasted image 20220924125245.png]]

Entonces vamos a ver más a profunidad como funciona el protocolo, abrimos el inspector
![[Pasted image 20220924125819.png]]

Tras la inspección de las cookies, se puede ver que existe un nombre de cookie admin con el valor falso

Para cambiar el valor de las cookies hacemos uso de una extensión web que nos permita modificar las cookies
![[Pasted image 20220924130026.png]]

Usamos esta extensión para cambiar el nombre y valor de la cookie, la modificamos de Flase a True y refrecamos el sitio, en ese caso podríamos entrar y vemos la bandera


![[Pasted image 20220924130448.png]]



![[Pasted image 20220924130357.png]]

```
picoCTF{th3_c0nsp1r4cy_l1v3s_6edb3f5f}
```
