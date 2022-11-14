# USERNAME -> amcdanymx


#### Description

We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/394/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)


#### Pistas
- Do you know what `mod 37` means?
- `mod 37` means modulo 37. It gives the remainder of a number after being divided by 37.

 
#### SOLUCIÓN

Tenemos que desencriptar unaa lista de numeros a modulo37, para ello creamos un script que lo haga:

```
amcdanymx@kali:~/picoCTF/basicmod1 % wget https://artifacts.picoctf.net/c/394/message.txt

--2022-11-13 18:20:20--  https://artifacts.picoctf.net/c/394/message.txt

Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.56, 13.249.74.22, 13.249.74.17, ...

Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[13.249.74.56]:443... conectado.

Petición HTTP enviada, esperando respuesta... 200 OK

Longitud: 86 [application/octet-stream]

Grabando a: «message.txt»
message.txt              100%[==============================================>]  86  --.-KB/s en 0s  

2022-11-13 18:20:20 (95.0 MB/s) - «message.txt» guardado [86/86]
amcdanymx@kali:~/picoCTF/basicmod1 % ls

message.txt

amcdanymx@kali:~/picoCTF/basicmod1 % cat message.txt

202 137 390 235 114 369 198 110 350 396 390 383 225 258 38 291 75 324 401 142 288 397 %**

```



```
datos = open('message.txt').read().split()
print(datos)

flag = ''

for n in datos:

     c = int(n) % 37

     if c >= 0 and c <=25:

             s = chr(c+65)

     elif c >= 26 and c <= 35:

             s = chr(c+22)

     else:

             s = '_'

     flag += s

print(f"picoCTF{{{flag}}}")
```

Obtenemos la salida del script donde vemos la bandera:

```
<< amcdanymx@kali~/picoCTF/basicmod1

>>> python3 exp.py                                                                18:30.10 dom nov 13 2022 >>>

['202', '137', '390', '235', '114', '369', '198', '110', '350', '396', '390', '383', '225', '258', '38', '291', '75', '324', '401', '142', '288', '397']

picoCTF{R0UND_N_R0UND_B6B25531}

```