# BANDIT LEVEL 19 -> LEVEL 20

# Objetivo

To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

## Helpful Reading Material

-   [setuid on Wikipedia](https://en.wikipedia.org/wiki/Setuid)


# Datos de acceso

USERNAME: **bandit19**
PASSWORD: VxCazJaVykI6W36BkBU0mJTCM8rR95XT

# Solución
Entramos al servidor Bandit e ingresamos contraseña

- listamos los archivos con ls -la
- encontramos el archivo llamado bandit20_do que pertenece a otro usuario
-  corremos el comando  ./bandit20-do id  para revisar los usuarios 
- utilizamos como id al usuario 20
-  ./bandit20-do cat /etc/bandit_pass/bandit20

# Notas adicionales
