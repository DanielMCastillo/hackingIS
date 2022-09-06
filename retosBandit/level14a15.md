# BANDIT LEVEL 14 -> LEVEL 15

## Objetivo

-   find the password that can be obtained by submitting the password of the current level to port 30000 on localhost.

## Datos de acceso

-   Host: bandit.labs.overthewire.org
-   Port: 2220
-   User: bandit14
-   Password: fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

## Solución

-   Use telnet command to conect to port 30000 "telnet localhost 30000", then put the actual password.

```
bandit14@bandit:~$ telnet localhost 30000
Trying 127.0.0.1...
Connected to localhost.
Escape character is '^]'.
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

Connection closed by foreign host.
bandit14@bandit:~$
```

## Notas adicionales

The telnet command is used to establish the connections between different machines.