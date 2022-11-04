# USERNAME -> amcdanymx


#### Descripción

Download this disk image, find the key and log into the remote machine.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

This challenge launches an instance on demand.  
Its current status is: `NOT_RUNNING`

#### Pistas

Sin pistas


#### Solución

Descargamos la imagen que nos dan y utilizamos las herramientas que ya hemos usado como mmls,  después con fls navegamos a través de los directorios buscando el archivo ssh, para después conectarnos al servidor que nos dan en el reto 

```  

operationoni ➤ ls                                                                                             

operationoni ➤ wget https://artifacts.picoctf.net/c/372/disk.img.gz                                           

--2022-11-03 21:24:17--  https://artifacts.picoctf.net/c/372/disk.img.gz

Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.56, 13.249.74.22, 13.249.74.17, ...

Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[13.249.74.56]:443... conectado.

Petición HTTP enviada, esperando respuesta... 200 OK

Longitud: 48132743 (46M) [application/octet-stream]

Grabando a: «disk.img.gz»

  

disk.img.gz              100%[=============================================>]  45.90M  7.36MB/s en 6.4s    

  

2022-11-03 21:24:24 (7.17 MB/s) - «disk.img.gz» guardado [48132743/48132743]

  

operationoni ➤ ls                                                                                             

disk.img.gz

operationoni ➤ gzip -d disk.img.gz                                                                            

operationoni ➤ ls -la                                                                                         

total 235528

drwxr-xr-x  2 amcdanymx amcdanymx  4096 nov  3 21:24 .

drwxr-xr-x 15 amcdanymx amcdanymx  4096 nov  3 21:23 ..

-rw-r--r--  1 amcdanymx amcdanymx 241172480 mar 15  2022 disk.img

operationoni ➤ mmls disk.img                                                                                  

DOS Partition Table

Offset Sector: 0

Units are in 512-byte sectors

  

   Slot  Start    End      Length   Description

000:  Meta  0000000000   0000000000   0000000001   Primary Table (#0)

001:  -------   0000000000   0000002047   0000002048   Unallocated

002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)

003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)

operationoni ➤ fls -o 206848 disk.img                                                                         

d/d 458:    home

d/d 11: lost+found

d/d 12: boot

d/d 13: etc

d/d 79: proc

d/d 80: dev

d/d 81: tmp

d/d 82: lib

d/d 85: var

d/d 94: usr

d/d 104:    bin

d/d 118:    sbin

d/d 464:    media

d/d 468:    mnt

d/d 469:    opt

d/d 470:    root

d/d 471:    run

d/d 473:    srv

d/d 474:    sys

V/V 33049:  $OrphanFiles

operationoni ➤ fls -o 206848 disk.img 470                                                                      

r/r 2344:   .ash_history

d/d 3916:   .ssh

operationoni ➤ fls -o 206848 disk.img 3916                                                                     

r/r 2345:   id_ed25519

r/r 2346:   id_ed25519.pub

operationoni ➤ icat -o 206848 disk.img 2345                                                                    

-----BEGIN OPENSSH PRIVATE KEY-----

b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW

QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC

gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA

AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy

KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==

-----END OPENSSH PRIVATE KEY-----

operationoni ➤ icat -o 206848 disk.img 2345 > key_file                                                         

operationoni ➤ cat key_file                                                                                    

-----BEGIN OPENSSH PRIVATE KEY-----

b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW

QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC

gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA

AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy

KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==

-----END OPENSSH PRIVATE KEY-----

operationoni ➤ chmod 400 key_file                                                                              

operationoni ➤ ls                                                                                              

disk.img  key_file

operationoni ➤ ls -la                                                                                          

total 235532

drwxr-xr-x  2 amcdanymx amcdanymx  4096 nov  3 21:27 .

drwxr-xr-x 15 amcdanymx amcdanymx  4096 nov  3 21:23 ..

-rw-r--r--  1 amcdanymx amcdanymx 241172480 mar 15  2022 disk.img

-r--------  1 amcdanymx amcdanymx   411 nov  3 21:27 key_file

operationoni ➤ ssh -i key_file -p 57471 ctf-player@saturn.picoctf.net                                          

The authenticity of host '[saturn.picoctf.net]:57471 ([18.217.86.78]:57471)' can't be established.

ED25519 key fingerprint is SHA256:5gIm/EJ9bYnoH4qed83W5HXLfN1DO55849f6Lze0lx8.

This key is not known by any other names

Are you sure you want to continue connecting (yes/no/[fingerprint])? yes

Warning: Permanently added '[saturn.picoctf.net]:57471' (ED25519) to the list of known hosts.

Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 5.13.0-1025-aws x86_64)

  

 * Documentation:  https://help.ubuntu.com

 * Management: https://landscape.canonical.com

 * Support:    https://ubuntu.com/advantage

  

This system has been minimized by removing packages and content that are

not required on a system that users do not log into.

  

To restore this content, you can run the 'unminimize' command.

  

The programs included with the Ubuntu system are free software;

the exact distribution terms for each program are described in the

individual files in /usr/share/doc/*/copyright.

  

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by

applicable law.

  

ctf-player@challenge:~$ ls

flag.txt

ctf-player@challenge:~$ cat flag.txt

picoCTF{k3y_5l3u7h_339601ed}ctf-player@challenge:~$

  
**
```

y obtenemos la bandera


```
picoCTF{k3y_5l3u7h_339601ed}ctf-player@challenge:~$

```
