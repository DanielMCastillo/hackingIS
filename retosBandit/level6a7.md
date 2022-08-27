# BANDIT LEVEL 6 -> LEVEL 7

# Objetivo

The password for the next level is stored **somewhere on the server** and has all of the following properties:

-   owned by user bandit7
-   owned by group bandit6
-   33 bytes in size

## Commands you may need to solve this level

[ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html) , [file](https://man7.org/linux/man-pages/man1/file.1.html) , [du](https://man7.org/linux/man-pages/man1/du.1.html) , [find](https://man7.org/linux/man-pages/man1/find.1.html) , [grep](https://man7.org/linux/man-pages/man1/grep.1.html)

## Commands utiles 

[ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cd](https://man7.org/linux/man-pages/man1/cd.1p.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html) , [file](https://man7.org/linux/man-pages/man1/file.1.html) , [du](https://man7.org/linux/man-pages/man1/du.1.html) , [find](https://man7.org/linux/man-pages/man1/find.1.html) , [grep](https://man7.org/linux/man-pages/man1/grep.1.html)

# Datos de acceso

DATOS DE ACCESO

USERNAME: **bandit6**
PASSWORD:  HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

# Solución

Con el comando find  podemos buscar archivos dentro del sistema. con -size nos  permite buscar por el peso del archivo. Aahora hay que buscar por el usaurio, con la opción -user, y que la opción -group nos permite buscar por el grupo al que se encuentra asociado

Y como no sabemos en qué carpeta del sistema se encuentra, lo buscamos desde la raíz  ('/'')

se nos presentó un problema que cada archivo nos dice que no tenemos permiso,, permission denied.

 find / -user bandit7 -group bandit6 -size 33c
 
El error es identificado con el número  2, y sus mensajes pueden ser redirigidos (usando el símbolo `>`) a la carpeta de /dev/null (archivo especial utilizado para descartar información):

ahora usamos el comando de la siguiente manera:
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
 y obtenemos el archivo 
 /var/lib/dpkg/info/bandit7.password

ahora podemos leerlo sin problema 
cat  /var/lib/dpkg/info/bandit7.password


# Notas adicionales

NOTAS ADICIONALES

[https://overthewire.org/wargames/bandit/bandit4.html](https://overthewire.org/wargames/bandit/bandit4.html)
