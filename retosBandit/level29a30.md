# Level 29 -> 30
## Objetivo

-   Tenemos un repositorio  `ssh://bandit29-git@localhost:2220/home/bandit29-git/repo`. La contraseña del usuario `bandit29-git`  es la misma para el usuario  `bandit29`.

Si clonamos el repositorio pasamos al otro nivel

Datos de acceso

-   Host: bandit.labs.overthewire.org
-   Port: 2220
-   User: bandit29
-   Password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

## Solución

-  Primero clona el repositorio, al clonarlo encontrarás dentro un archivo README, que contiene la contraseña, pero no la hay. Busque en las diferentes sucursales y diferentes versiones la contraseña.
```
bandit29@bandit:/tmp/rep29/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/rep29/repo$ git log
commit 1748acec99ba66676acd551c2932fb9fc14a98a3 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    fix username

commit c27fff763003bb1d57d311e6763211110b94cc87
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    initial commit of README.md
bandit29@bandit:/tmp/rep29/repo$ commit checkout c27fff763003bb1d57d311e6763211110b94cc87
commit: command not found
bandit29@bandit:/tmp/rep29/repo$ git checkout c27fff763003bb1d57d311e6763211110b94cc87
Note: switching to 'c27fff763003bb1d57d311e6763211110b94cc87'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at c27fff7 initial commit of README.md
bandit29@bandit:/tmp/rep29/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit29
- password: <no passwords in production!>

bandit29@bandit:/tmp/rep29/repo$ git checkout master
Previous HEAD position was c27fff7 initial commit of README.md
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
bandit29@bandit:/tmp/rep29/repo$ ls
README.md
bandit29@bandit:/tmp/rep29/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/rep29/repo$ git log
commit 1748acec99ba66676acd551c2932fb9fc14a98a3 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    fix username

commit c27fff763003bb1d57d311e6763211110b94cc87
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    initial commit of README.md
bandit29@bandit:/tmp/rep29/repo$ git status
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
bandit29@bandit:/tmp/rep29/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
bandit29@bandit:/tmp/rep29/repo$ git checkout dev
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/rep29/repo$ git log
commit 2b1395f00cfb986163082c50100be5be8f249f64 (HEAD -> dev, origin/dev)
Author: Morla Porla <morla@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    add data needed for development

commit 989df8073e16b5f7ec337f51bc1f60bd2f6b7e0b
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    add gif2ascii

commit 1748acec99ba66676acd551c2932fb9fc14a98a3 (origin/master, origin/HEAD, master)
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    fix username

commit c27fff763003bb1d57d311e6763211110b94cc87
Author: Ben Dover <noone@overthewire.org>
Date:   Thu Sep 1 06:30:26 2022 +0000

    initial commit of README.md
bandit29@bandit:/tmp/rep29/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

bandit29@bandit:/tmp/rep29/repo$
```

Notas adicionales
