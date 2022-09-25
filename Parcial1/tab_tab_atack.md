# USERNAME picoCTF -> amcdanymx

# Tab Tab Atack

## Description
El uso de tabcomplete en la Terminal agregará años a su vida, especialmente. cuando se trata de estructuras de directorios y nombres de archivos largos e inconexos: [Addadshashanammu.zip](https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip)

## Pistas
Después de 'descomprimir', este problema se puede resolver presionando 11 botones... (principalmente Tabulador)...

## Soución

Descargamos el archivo comprimido que se nos da en el link
Lo descomprimimos y buscamos el archivo que se encuentra hasta el final
para ello usamos el tabulador para movernos entre carpetas:

```
──(amcdanymx@kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
ls
fang-of-haynekhtnamet
```

Vemos el archivo 
```

file fang-of-haynekhtnamet fang-of-haynekhtnamet: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=47e898db922f38cb54ab4a08fb4e3def5a1cb6a1, not stripped

```

cambiamos los permisos del archivo 
```
chmod +x fang-of-haynekhtnamet
```

ejecutamos el archivo y encontramos la llave
```
./fang-of-haynekhtnamet
**ZAP!** picoCTF{l3v3l_up!_t4k3_4_r35t!_a00cae70}
```

