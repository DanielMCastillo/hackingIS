# USERNAME -> amcdanymx


#### Description

Morse code is well known. Can you decrypt this?Download the file [here](https://artifacts.picoctf.net/c/235/morse_chal.wav).Wrap your answer with picoCTF{}, put underscores in place of pauses, and use all lowercase.


#### PISTAS
Audacity is a really good program to analyze morse code audio.


#### SOLUCIÓN

Se nos da un archivo de auido, dicho archivo contiene una codificación en código morse, en mi caso encontré una herramienta online que decodifica
[https://morsecode.world/international/decoder/audio-decoder-adaptive.html](https://morsecode.world/international/decoder/audio-decoder-adaptive.html)


```
Nos da lo siguiente
WH47 H47H 90D W20U9H7
```

Lo acomodamos como nos dicen, en minusculas y con guiones en lugar de espacios y siguiendo el formato de la bandera picoCTF{}
```
picoCTF{wh47_h47h_90d_w20u9h7}
```
