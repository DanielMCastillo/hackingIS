# USERNAME -> amcdanymx

#### Description

Can you get the flag?Reverse engineer this [Python program](https://artifacts.picoctf.net/c/466/unpackme.flag.py).

#### PISTAS
- None

#### SOLUCIÓN

En este desafío nos dan un archivo ccon extensión .py dicho archivo contiene una encriptación de una contraseña, hay como muchas funciones que encirptan en el código, realmente estuve analizando y vi una línea donde executaba una instrucción, lo que hice fue cambiar a que lo imprimiera, y así nos muestra la bandera:
```  
import base64

from cryptography.fernet import Fernet

payload = b'gAAAAABiMD09KmaS5E6AQNpRx1_qoXOBFpSny3kyhr8Dk_IEUu61Iu0TaSIf8RCyf1LJhKUFVKmOt2hfZzynRbZ_fSYYN_OLHTTIRZOJ6tedEaK6UlMSkYJhRjAU4PfeETD-8gDOA6DQ8eZrr47HJC-kbyi3Q5o3Ba28mutKCAkwrqt3gYOY9wp3dWYSWzP4Tc3NOYWfu-SJbW997AM8GA-APpGfFrf9f7h0VYcdKOKu4Vq9zjJwmTG2VXWFET-pkF5IxV3ZKhz36L5IvZy1dVZXqaMR96lovw=='

key_str = 'correctstaplecorrectstaplecorrec'

key_base64 = base64.b64encode(key_str.encode())

f = Fernet(key_base64)

plain = f.decrypt(payload)

#exec(plain.decode())

print(plain.decode())

```

```

amcdanymx:unpackmepy/ $ ls                                               
unpackme.flag.py

amcdanymx:unpackmepy/ $ code unpackme.flag.py                          

amcdanymx:unpackmepy/ $ python unpackme.flag.py                         

What's the password? asdasda

That password is incorrect.

amcdanymx:unpackmepy/ $ python unpackme.flag.py                         

pw = input('What\'s the password? ')

if pw == 'batteryhorse':

  print('picoCTF{175_chr157m45_85f5d0ac}')

else:

  print('That password is incorrect.')

```

y obtenemos la bandera: picoCTF{175_chr157m45_85f5d0ac}

