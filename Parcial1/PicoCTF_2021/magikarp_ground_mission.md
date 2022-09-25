# USERNAME picoCTF -> amcdanymx
# Magikarp Ground Mission

## Desafío
¿Sabes cómo moverte entre directorios y leer archivos en el shell? Inicie el contenedor, `ssh` y luego `ls` una vez conectado para comenzar. Inicie sesión a través de `ssh` como `ctf-player` con la contraseña, `6dee9772`

Este desafío lanza una instancia bajo demanda.
Su estado actual es: NOT_RUNNING

## Pista

¡Encontrar una hoja de trucos para bash sería realmente útil!

## Solución

Nos conectamos con 
```
ssh ctf-player@venus.picoctf.net -p 57593
**

┌──(amcdanymx㉿kali)-[~/Descargas]

└─$ ssh ctf-player@venus.picoctf.net -p 57593

ctf-player@venus.picoctf.net's password:

Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.4.0-1041-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management: https://landscape.canonical.com
 * Support:    https://ubuntu.com/advantage
This system has been minimized by removing packages and content that are
not required on a system that users do not log into.
  
To restore this content, you can run the 'unminimize' command.
Last login: Sun Sep 25 18:42:58 2022 from 127.0.0.1
**

```
Usando ls para enumerar los archivos

```
ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt

```

Con cat 1of3.flag.txt, obtenemos


```
ctf-player@pico-chall$ cat 1of3.flag.txt
picoCTF{xxsh_

```

Nos dice algo como
A continuación, vaya a la raíz de todas las cosas, más especificamente esto  `/`
Escribí cd .. (regresar a un directorio) luego ls -a  y encontré 3of3.flag.txt

```
ctf-player@pico-chall$ cat 3of3.flag.txt
540e4e79}
```

Seguí retrocediendo (con cd ..) y enumerando los archivos y directorios (ls -a) hasta que apareció 2of3.flag.txt.

```

ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ ls
2of3.flag.txt  dev   instructions-to-3of3.txt  media  proc  sbin  tmp

bin        etc   lib                   mnt root  srv   usr

boot       home  lib64                 opt run   sys   var

ctf-player@pico-chall$ cat 2of3.flag.txt

0ut_0f_\/\/4t3r_


```

Bandera
```
picoCTF{xxsh_0ut_0f_\/\/4t3r_540e4e79}
```
