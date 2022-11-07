# USERNAME -> amcdanymx


#### Description

Download this image and find the flag.

-   [Download image](https://artifacts.picoctf.net/c/423/pico.flag.png)


#### PISTAS
- We know the end sequence of the message will be `$t3g0`.

#### SOLUCIÓN
Descargamos el archivo, utilizamos unaa herramienta llamada stego tool para decodificar imagenes, usamos algunos comandos para obtener la decodificacion y que la herramienta ayuda con eso:


```

**  
  

picoCTF/st3go [ git clone https://github.com/djrobin17/image-stego-tool.git                                     

Clonando en 'image-stego-tool'...

remote: Enumerating objects: 24, done.

remote: Counting objects: 100% (24/24), done.

remote: Compressing objects: 100% (23/23), done.

remote: Total 24 (delta 6), reused 1 (delta 0), pack-reused 0

Recibiendo objetos: 100% (24/24), 25.68 KiB | 1.12 MiB/s, listo.

Resolviendo deltas: 100% (6/6), listo.

picoCTF/st3go [ sudo pip3 install numpy                                                                 ] 1:43

[sudo] contraseña para amcdanymx:

Requirement already satisfied: numpy in /usr/lib/python3/dist-packages (1.21.5)

WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv

picoCTF/st3go [ sudo pip3 install pillow                                                                ] 1:43

Requirement already satisfied: pillow in /usr/lib/python3/dist-packages (9.2.0)

WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv

picoCTF/st3go [ python3 stego.py ../pico.flag.png                                                       ] 1:43

python3: can't open file '/home/amcdanymx/picoCTF/st3go/stego.py': [Errno 2] No such file or directory

picoCTF/st3go [ ls                                                                                      ] 1:43

image-stego-tool  pico.flag.png

picoCTF/st3go [ python3 stego pico.flag.png                                                             ] 1:44

python3: can't open file '/home/amcdanymx/picoCTF/st3go/stego': [Errno 2] No such file or directory

picoCTF/st3go [ python3 stego.py pico.flag.png                                                          ] 1:44

python3: can't open file '/home/amcdanymx/picoCTF/st3go/stego.py': [Errno 2] No such file or directory

picoCTF/st3go [ cd image-stego-tool                                                                     ] 1:44

st3go/image-stego-tool [ ls                                                                      master ] 1:44

README.md  stego.py  stego-start.png

st3go/image-stego-tool [ python3 stego.py pico.flag.png                                          master ] 1:44

--Welcome to $t3g0--

1: Encode

2: Decode

2

Enter Source Image Path

../pico.flag.png

Decoding...

Hidden Message: picoCTF{7h3r3_15_n0_5p00n_a9a181eb}

```

y tenemos la bandera:

```
picoCTF{7h3r3_15_n0_5p00n_a9a181eb}
```