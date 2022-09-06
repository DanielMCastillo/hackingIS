# Level 16 -> 17 

## Objetivo

-   Find the next password, which is the only file that has been changed between the files passwords.old and passwords.new

## Datos de acceso

-   Host: bandit.labs.overthewire.org
-   Port: 2220
-   User: bandit17
-   Password: Use the sshkey provided at the previous level.

## Solución

-   Use the command diff using the two files and get the password.

```
bandit17@bandit:~$ diff passwords.new passwords.old
42c42
< hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
---
> 09wUIyMU4YhOzl1Lzxoz0voIBzZ2TUAf
```

##  Notas adicionales

-   Diif is a command that allows you to compare two files line by line.