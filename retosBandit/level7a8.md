# BANDIT LEVEL 7 -> LEVEL 8

# Objetivo


The password for the next level is stored in the file **data.txt** next to the word **millionth**

## Comandos utiles

[man](https://man7.org/linux/man-pages/man1/man.1.html), grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd



# Datos de acceso

DATOS DE ACCESO

USERNAME: **bandit7**
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
