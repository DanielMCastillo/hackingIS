# BANDIT LEVEL 13 -> LEVEL 14


## Objetivo

-   Find the password found in a directory readable only by bandit14, whose password we don't have yet.

## Datos de acceso

-   Host: bandit.labs.overthewire.org
-   Port: 2220
-   User: bandit13
-   Password: wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

## Solución

-   Use the sshkey.private file to log into bandit14. " ssh -i sshkey.private [bandit14@bandit.labs.overthewire.org](mailto:bandit14@bandit.labs.overthewire.org) -p 2220", then read the password

```
bandit13@bandit:~$ ls
sshkey.private
bandit13@bandit:~$ ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
The authenticity of host '[bandit.labs.overthewire.org]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
```

-   Read the password.

```
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
bandit14@bandit:~$
```

## Notas adicionales

You can log into a server using the ssh key.