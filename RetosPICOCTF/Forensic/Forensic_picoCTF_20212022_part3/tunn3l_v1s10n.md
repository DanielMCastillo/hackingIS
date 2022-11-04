# USERNAME -> amcdanymx

#### DESCRIPCIÓN

We found this [file](https://mercury.picoctf.net/static/21c07c9dd20cd9f2459a0ae75d99af6e/tunn3l_v1s10n). Recover the flag.


#### PISTAS

- Weird that it won't display right...


#### SOLUCIÓN

Usamos el editor hexadecimal para mover los valores adecuadors de offset en cada campo para modificar la imagen y hacemos que descubra por completo la bandera, para ello movemos los valores de tamaño de offset correspoindientes:


```
**tunnelvision ➤ ls                                                                                             
tunnelvision ➤ wget https://mercury.picoctf.net/static/21c07c9dd20cd9f2459a0ae75d99af6e/tunn3l_v1s10n         

--2022-11-03 18:50:12--  https://mercury.picoctf.net/static/21c07c9dd20cd9f2459a0ae75d99af6e/tunn3l_v1s10n

Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142

Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:443... conectado.

Petición HTTP enviada, esperando respuesta... 200 OK

Longitud: 2893454 (2.8M) [application/octet-stream]

Grabando a: «tunn3l_v1s10n»

tunn3l_v1s10n            100%[=============================================>]   2.76M  2.91MB/s en 0.9s    

2022-11-03 18:50:14 (2.91 MB/s) - «tunn3l_v1s10n» guardado [2893454/2893454]

tunnelvision ➤ ls                                                                                             
tunn3l_v1s10n
tunnelvision ➤ file tunn3l_v1s10n                                                                             

tunn3l_v1s10n: data

tunnelvision ➤ xxd tunn3l_v1s10n | head                                                                       

00000000: 424d 8e26 2c00 0000 0000 bad0 0000 bad0  BM.&,...........

00000010: 0000 6e04 0000 3201 0000 0100 1800 0000  ..n...2.........

00000020: 0000 5826 2c00 2516 0000 2516 0000 0000  ..X&,.%...%.....

00000030: 0000 0000 0000 231a 1727 1e1b 2920 1d2a  ......#..'..) .*

00000040: 211e 261d 1a31 2825 352c 2933 2a27 382f  !.&..1(%5,)3*'8/

00000050: 2c2f 2623 332a 262d 2420 3b32 2e32 2925  ,/&#3*&-$ ;2.2)%

00000060: 3027 2333 2a26 382c 2836 2b27 392d 2b2f  0'#3*&8,(6+'9-+/

00000070: 2623 1d12 0e23 1711 2916 0e55 3d31 9776  &#...#..)..U=1.v

00000080: 668b 6652 996d 569e 7058 9e6f 549c 6f54  f.fR.mV.pX.oT.oT

00000090: ab7e 63ba 8c6d bd8a 69c8 9771 c193 71c1  .~c..m..i..q..q.

tunnelvision ➤ xxd tunn3l_v1s10n.bmp                                                                          

xxd: tunn3l_v1s10n.bmp: No such file or directory

tunnelvision ➤ hexeditor tunn3l_v1s10n.bmp                                                                    

tunnelvision ➤ open tunn3l_v1s10n.bmp                                                                         

tunnelvision ➤ hexeditor tunn3l_v1s10n.bmp                                                                    

tunnelvision ➤ hexeditor tunn3l_v1s10n.bmp                                                                    

tunnelvision ➤ hexeditor tunn3l_v1s10n.bmp                                                                    

tunnelvision ➤ open tunn3l_v1s10n.bmp                                                                         

tunnelvision ➤ open tunn3l_v1s10n.bmp                                                                         

tunnelvision ➤ ld                                                                                             

ld: no hay ficheros de entrada

tunnelvision ➤ ls                                                                                             

tunn3l_v1s10n

tunnelvision ➤ exiftool tunn3l_v1s10n                                                                         

ExifTool Version Number     : 12.44

File Name                   : tunn3l_v1s10n

Directory                   : .

File Size                   : 2.9 MB

File Modification Date/Time : 2022:11:03 18:54:10-06:00

File Access Date/Time       : 2022:11:03 18:54:15-06:00

File Inode Change Date/Time : 2022:11:03 18:54:10-06:00

File Permissions            : -rw-r--r--

File Type                   : BMP

File Type Extension         : bmp

MIME Type                   : image/bmp

BMP Version                 : Windows V3

Image Width                 : 1134

Image Height                : 306

Planes                      : 1

Bit Depth                   : 24

Compression                 : None

Image Length                : 2893400

Pixels Per Meter X          : 5669

Pixels Per Meter Y          : 5669

Num Colors                  : Use BitDepth

Num Important Colors        : All

Image Size                  : 1134x306

Megapixels                  : 0.347

tunnelvision ➤ hexeditor tunn3l_v1s10n.bmp                                                                    

tunnelvision ➤ exiftool tunn3l_v1s10n                                                                         

ExifTool Version Number     : 12.44

File Name                   : tunn3l_v1s10n

Directory                   : .

File Size                   : 2.9 MB

File Modification Date/Time : 2022:11:03 18:56:18-06:00

File Access Date/Time       : 2022:11:03 18:56:18-06:00

File Inode Change Date/Time : 2022:11:03 18:56:18-06:00

File Permissions            : -rw-r--r--

File Type                   : BMP

File Type Extension         : bmp

MIME Type                   : image/bmp

BMP Version                 : Windows V3

Image Width                 : 1134

Image Height                : 320

Planes                      : 1

Bit Depth                   : 24

Compression                 : None

Image Length                : 2893400

Pixels Per Meter X          : 5669

Pixels Per Meter Y          : 5669

Num Colors                  : Use BitDepth

Num Important Colors        : All

Image Size                  : 1134x320

Megapixels                  : 0.363

tunnelvision ➤ open tunn3l_v1s10n.bmp                                                                         

tunnelvision ➤ mv tunn3l_v1s10n tunn3l_v1s10n.bmp                                                             

tunnelvision ➤ open tunn3l_v1s10n.bmp                                                                         

tunnelvision ➤ hexeditor tunn3l_v1s10n.bmp                                                                    

tunnelvision ➤ open tunn3l_v1s10n.bmp                                                                         

tunnelvision ➤ quit3**

```


Con el tamaño adecuado de la imagen podemos ver la bandera:
```
picoCTF{qu1t3_a_v13w_2020}
```
