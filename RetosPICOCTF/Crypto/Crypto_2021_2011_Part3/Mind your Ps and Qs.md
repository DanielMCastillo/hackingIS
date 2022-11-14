# USERNAME -> amcdanymx


#### Description

In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values)



#### Pistas
Bits are expensive, I used only a little bit over 100 to save money

 
#### SOLUCIÓN

Utilizamos una herramienta para factorizar llamada http://factordb.com
Descargamos el archivo que nos dan, para este desafío necesitaremos ciertas librerías que manejan texto plano de muchos caracteres y que especificamente nos ayudarán en el desafío, como anteriormente vimos en la teoría de RSA la variable c es texto cifrado, e elexponente de la llave publica, n es el modulo de multiplicado de p por q
Debemos saber como ahora usando una factorización se puede conseguir la 
llave:

```
**amcdanymx@kali:~/picoCTF/mindpsandqs % wget https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values

--2022-11-13 17:40:05--  https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values

Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 205 [application/octet-stream]
Grabando a: «values»
values                   100%[==============================================>] 205  --.-KB/s en 0s  

  

2022-11-13 17:40:06 (118 MB/s) - «values» guardado [205/205]
amcdanymx@kali:~/picoCTF/mindpsandqs % ls
values
amcdanymx@kali:~/picoCTF/mindpsandqs % cat values

Decrypt my super sick RSA:
c: 421345306292040663864066688931456845278496274597031632020995583473619804626233684
n: 631371953793368771804570727896887140714495090919073481680274581226742748040342637
e: 65537%**
```

Python 
```
>>> from Crypto.Util.number import long_to_bytes
>>> from Crypto.Util.number import inverse

>>> c = 421345306292040663864066688931456845278496274597031632020995583473619804626233684

>>> e = 65537

>>> p = 1461849912200000206276283741896701133693

>>> q = 431899300006243611356963607089521499045809

>>> n = p*q

>>> n

631371953793368771804570727896887140714495090919073481680274581226742748040342637

>>> tn = (p-1)*(q-1)

>>> d = inverse(e,tn)

>>> m = pow(c,d,n)

>>> m

13016382529449106065927291425342535437996222135352905256639647889241102700065917

>>> long_to_bytes(m)

b'picoCTF{sma11_N_n0_g0od_55304594}'

```
 desencritpando el valor de m obtenemos la bandera:
```
picoCTF{sma11_N_n0_g0od_55304594}

```
