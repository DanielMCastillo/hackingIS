# USERNAME -> amcdanymx

## m00nwalk

#### Description

Decode this [message](https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav) from the moon.
  
#### PISTAS
- How did pictures from the moon landing get sent back to Earth?
- What is the CMU mascot?, that might help select a RX option


#### SOLUCIÓN


Este reto consiste en decodificar audios para encontrar la bandera, se nos muestra una tecnología llamada sstv la cuál se utilizó para decodificar imagenes desde el apollo 11  en la luna hasta la tierra, de manera que se mandaban señales de audio ya que son más rapidas, se utilizaba esta forma de codificación para las imagenes, aquí hacemos lo mismo, se nos da un archivo el cual es un audio que no contiene nada de sonido, sabemos que esta codificado, utilizaremos una herramienta que está en un repositorio publico la cual es la siguiente:

https://github.com/colaclanth/sstv

En el repositorio se nos explica como instalarlo, como correrlo y obtener la decodificación, los pasos se muestran en mi consola:

```

amcdanymx@kali:~/picoCTF

 $ ls

forensic  whatlieswithin

amcdanymx@kali:~/picoCTF

 $ mkdir moonwalk

amcdanymx@kali:~/picoCTF

 $ cd moonwalk

amcdanymx@kali:~/picoCTF/moonwalk

 $ wget https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav

--2022-10-10 18:16:59--  https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav

Resolviendo jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8

Conectando con jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)[3.131.60.8]:443... conectado.

Petición HTTP enviada, esperando respuesta... 200 OK

Longitud: 11066998 (11M) [application/octet-stream]

Grabando a: «message.wav»

  

message.wav              100%[==============================================>]  10.55M  5.78MB/s en 1.8s    

  

2022-10-10 18:17:01 (5.78 MB/s) - «message.wav» guardado [11066998/11066998]

  

amcdanymx@kali:~/picoCTF/moonwalk

 $ ls

message.wav

amcdanymx@kali:~/picoCTF/moonwalk

 $ file message.wav

message.wav: RIFF (little-endian) data, WAVE audio, Microsoft PCM, 16 bit, mono 48000 Hz

amcdanymx@kali:~/picoCTF/moonwalk

 $ open message.wav

amcdanymx@kali:~/picoCTF/moonwalk

 $

(parole:20648): xfconf-WARNING **: 18:17:48.247: Failed to set property "parole::/audio/volume": Se canceló la operación

  

(parole:20648): xfconf-WARNING **: 18:17:48.306: Failed to set property "parole::/audio/volume": Se canceló la operación

  

(parole:20648): xfconf-WARNING **: 18:17:48.433: Failed to set property "parole::/audio/volume": Se canceló la operación

  

(parole:20648): xfconf-WARNING **: 18:17:48.449: Failed to set property "parole::/audio/volume": Se canceló la operación


amcdanymx@kali:~/picoCTF/moonwalk

 $ open message.wav                                                                                       130 ↵

amcdanymx@kali:~/picoCTF/moonwalk

 $ ls

message.wav

amcdanymx@kali:~/picoCTF/moonwalk

 $ cd /opt

amcdanymx@kali:/opt

 $ git clone https://github.com/colaclanth/sstv.git  

fatal: no se pudo crear un árbol de trabajo 'sstv': Permiso denegado

amcdanymx@kali:/opt

 $ sudo su git clone https://github.com/colaclanth/sstv.git                                               128 ↵

[sudo] contraseña para amcdanymx:

su: user git does not exist or the user entry does not contain all the required fields

amcdanymx@kali:/opt

 $ sudo git clone https://github.com/colaclanth/sstv.git                                                    1 ↵

Clonando en 'sstv'...

remote: Enumerating objects: 221, done.

remote: Total 221 (delta 0), reused 0 (delta 0), pack-reused 221

Recibiendo objetos: 100% (221/221), 1.01 MiB | 1.93 MiB/s, listo.

Resolviendo deltas: 100% (140/140), listo.

amcdanymx@kali:/opt

 $ ls

microsoft  sstv

amcdanymx@kali:/opt

 $ sudo python setup.py install

python: can't open file '/opt/setup.py': [Errno 2] No such file or directory

amcdanymx@kali:/opt

 $ cd sstv                                                                                                  2 ↵

amcdanymx@kali:/opt/sstv

master ✔ $ ls

examples  LICENSE  README.md  setup.py  sstv  test

amcdanymx@kali:/opt/sstv

master ✔ $ sudo python setup.py install

running install

/usr/lib/python3/dist-packages/setuptools/command/install.py:34: SetuptoolsDeprecationWarning: setup.py install is deprecated. Use build and pip and other standards-based tools.

Installed /usr/local/lib/python3.10/dist-packages/sstv-0.1-py3.10.egg

  

amcdanymx@kali:/opt/sstv

master ✔ $ sstv

amcdanymx@kali:/opt/sstv/sstv

master ✔ $ sstv -help

usage: sstv [-h] [-d AUDIO_FILE] [-o OUTPUT_FILE] [-s SKIP] [-V] [--list-modes] [--list-audio-formats]

         [--list-image-formats]

sstv: error: argument -h/--help: ignored explicit argument 'elp'



amcdanymx@kali:~

 $ ls

bandit          Descargas   Escritorio  icpc  isredes  Música   Plantillas Público  Vídeos

championsliguifile  Documentos  hash    Imágenes  jwt.txt  picoCTF  programacion  testing

amcdanymx@kali:~

 $ cd picoCTF

amcdanymx@kali:~/picoCTF

 $ ls

forensic  moonwalk  whatlieswithin

amcdanymx@kali:~/picoCTF

 $ cd moonwalk

amcdanymx@kali:~/picoCTF/moonwalk

 $ ls

message.wav

amcdanymx@kali:~/picoCTF/moonwalk

 $ $ sstv -d message.wav -o result.png

zsh: command not found: $

amcdanymx@kali:~/picoCTF/moonwalk

 $ ls                                                                                       

message.wav

amcdanymx@kali:~/picoCTF/moonwalk

 $  sstv -d message.wav -o result.png

[sstv] Searching for calibration header... Found!    

[sstv] Detected SSTV mode Scottie 1

[sstv] Decoding image...   [####################################################################

[sstv] Drawing image data...

[sstv] ...Done!

amcdanymx@kali:~/picoCTF/moonwalk

 $ ls

message.wav  result.png

amcdanymx@kali:~/picoCTF/moonwalk

 $ open result.png
  

```


Obtenemos la bandera:

```

picoCTF{beep_boop_im_in_5pace}

```
