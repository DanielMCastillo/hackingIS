
# USERNAME -> amcdanymx

#### Description

Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it.Download the data [here](https://artifacts.picoctf.net/c/296/anthem.flag.txt).


#### PISTAS
- Download the file and search for the flag based on the known prefix.

#### SOLUCIÓN

Descargamos el archivo, abrimos el archivo al ver que es un archvio de texto, tiene de contenido mucho texto entonces podemos buscar con filtro, en mi caso abri el archivo en vscode y solo puse cntrl+F y busqué "pico", encontramos la bandera en un parrafo
```

lookeyhere % wget https://artifacts.picoctf.net/c/296/anthem.flag.txt

--2022-11-07 13:19:36--  https://artifacts.picoctf.net/c/296/anthem.flag.txt

Resolviendo artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.74.22, 13.249.74.56, 13.249.74.17, ...

Conectando con artifacts.picoctf.net (artifacts.picoctf.net)[13.249.74.22]:443... conectado.

Petición HTTP enviada, esperando respuesta... 200 OK

Longitud: 108668 (106K) [application/octet-stream]

Grabando a: «anthem.flag.txt»

  

anthem.flag.t 100% 106.12K  --.-KB/s en 0.1s    

  

2022-11-07 13:19:37 (1009 KB/s) - «anthem.flag.txt» guardado [108668/108668]

  

lookeyhere % ls

anthem.flag.txt

lookeyhere % open anthem.flag.txt

lookeyhere % [9459:1107/131958.280458:ERROR:object_proxy.cc(623)] Failed to call method: org.freedesktop.DBus.StartServiceByName: object_path= /org/freedesktop/DBus: org.freedesktop.DBus.Error.NoReply: Did not receive a reply. Possible causes include: the remote application did not send a reply, the message bus security policy blocked the reply, the reply timeout expired, or the network connection was broken.

libva error: vaGetDriverNameByIndex() failed with unknown libva error, driver_name = (null)

[9515:1107/132000.087183:ERROR:gpu_memory_buffer_support_x11.cc(44)] dri3 extension not supported.

[main 2022-11-07T19:20:01.041Z] update#setState idle

[main 2022-11-07T19:20:07.325Z] Starting extension host with pid 9667 (fork() took 21 ms).

[main 2022-11-07T19:20:31.079Z] update#setState checking for updates

[main 2022-11-07T19:20:31.087Z] update#setState available for download
```
  y la enccontramos:
  
```
 These things help us in our work. We do not understand them, but

   we think that the men of picoCTF{gr3p_15_@w3s0m3_2116b979}**