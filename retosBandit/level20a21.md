# BANDIT LEVEL 19 -> LEVEL 20

# Objetivo

To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

## Helpful Reading Material

-   [setuid on Wikipedia](https://en.wikipedia.org/wiki/Setuid)


# Datos de acceso

USERNAME: **bandit20**
PASSWORD:  NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

# Solución
Entramos al servidor Bandit e ingresamos contraseña

listamos con ls
- vemos un ejecutable llamado suconnect
Aperturamos un puerto para esuchar y encontrar la contrasñea
- nc -lp 6666 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
- esuchamos y ejecutamos ./suconnect 6666(nombre del puerto abierto)




# Notas adicionales
