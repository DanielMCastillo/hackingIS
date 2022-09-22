# Level 31 -> 32


## Objetivo

-   Hay un repositorio de git en `ssh://bandit31-git@localhost/home/bandit31-git/repo`. La contraseña del usuario `bandit31-git` es la misma que la del usuario `bandit31`.

Clonamos el repositorio y encuentraremos la contraseña para el siguiente nivel.

## Datos de acceso

-   Host: bandit.labs.overthewire.org
-   Port: 2220
-   User: bandit31
-   Password: OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

## Solución
- Cuando lea el archivo README, verá instrucciones sobre qué hacer. Cuando intenté cargar el archivo "key.txt" al repositorio, se mostrará que los archivos con la extensión txt no se pueden cargar, use "-f" para forzar esto.

```
bandit31@bandit:/tmp/rep31/repo$ cat README.md
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

bandit31@bandit:/tmp/rep31/repo$ git branch
* master
bandit31@bandit:/tmp/rep31/repo$ nano key.txt
Unable to create directory /home/bandit31/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit31@bandit:/tmp/rep31/repo$ ls
key.txt  README.md
bandit31@bandit:/tmp/rep31/repo$ git add .
bandit31@bandit:/tmp/rep31/repo$ git commit
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
bandit31@bandit:/tmp/rep31/repo$ git add key.txt
The following paths are ignored by one of your .gitignore files:
key.txt
hint: Use -f if you really want to add them.
hint: Turn this message off by running
hint: "git config advice.addIgnoredFile false"
bandit31@bandit:/tmp/rep31/repo$ git add key.txt -f
bandit31@bandit:/tmp/rep31/repo$ git commit
Unable to create directory /home/bandit31/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

[master 76305fa] Added file
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt
bandit31@bandit:/tmp/rep31/repo$ git push
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password:
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 322 bytes | 322.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
remote: Well done! Here is the password for the next level:
remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'
bandit31@bandit:/tmp/rep31/repo$
```

