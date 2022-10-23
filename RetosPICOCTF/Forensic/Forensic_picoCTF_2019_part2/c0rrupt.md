# USERNAME -> amcdanymx


#### Description

We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.
  
#### PISTAS
- Try fixing the file header


#### SOLUCIÓN

Descargamos el archivo del link el cual contiene un archivo llamado mystery si lo leemos nos dice que contiene "data", sabemos que debemos corregir el header del archivo para poder leerlo, es ahí donde entra la teoría de imagenees y buscamos información.
```

**mcdanymx:Descargas/ $ file mystery                                                                 [12:35:45]

mystery: data

amcdanymx:Descargas/ $ xxd mystery | head                                                           [12:35:52]

00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR

00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..

00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......

00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...

00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I

00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?

00000060: 8e64 cd71 bd2d 8b20 2080 9041 8302 08d0  .d.q.-.  ..A....

00000070: f9ed 40a0 f36e 407b 9023 8f1e d720 8b3e  ..@..n@{.#... .>

00000080: b7c1 0d70 0374 b503 ae41 6bf8 bea8 fbdc  ...p.t...Ak.....

00000090: 3e7d 2a22 336f de5b 55dd 3d3d f920 9188  >}*"3o.[U.==. ..

amcdanymx:Descargas/ $ hexeditor mystery                                                            [12:36:17]

amcdanymx:Descargas/ $ file mystery                                                                 [12:37:51]

mystery: data

amcdanymx:Descargas/ $ hexeditor mystery                                                            [12:37:57]

amcdanymx:Descargas/ $ file mystery                                                                 [12:39:17]

mystery: data

amcdanymx:Descargas/ $ hexeditor mystery                                                            [12:39:19]

amcdanymx:Descargas/ $ file mystery                                                                 [12:40:04]

mystery: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced

amcdanymx:Descargas/ $ open mystery                                                                 [12:40:06]


```


Instalamos un software para revisar la  integridad de un archivo y comprobar que esté en orden.

```
amcdanymx:Descargas/ $ sudo apt install pngcheck                                                    [12:40:17]

[sudo] contraseña para amcdanymx:

Leyendo lista de paquetes... Hecho

Creando árbol de dependencias... Hecho

Leyendo la información de estado... Hecho

Los paquetes indicados a continuación se instalaron de forma automática y ya no son necesarios.

  libnode108 nodejs nodejs-doc

Utilice «sudo apt autoremove» para eliminarlos.

Se instalarán los siguientes paquetes NUEVOS:

  pngcheck

0 actualizados, 1 nuevos se instalarán, 0 para eliminar y 1025 no actualizados.

Se necesita descargar 69.4 kB de archivos.

Se utilizarán 211 kB de espacio de disco adicional después de esta operación.

Des:1 http://http.kali.org/kali kali-rolling/main amd64 pngcheck amd64 3.0.2-2+b1 [69.4 kB]

Descargados 69.4 kB en 1s (63.6 kB/s)

Seleccionando el paquete pngcheck previamente no seleccionado.

(Leyendo la base de datos ... 314082 ficheros o directorios instalados actualmente.)

Preparando para desempaquetar .../pngcheck_3.0.2-2+b1_amd64.deb ...

Desempaquetando pngcheck (3.0.2-2+b1) ...

Configurando pngcheck (3.0.2-2+b1) ...

Procesando disparadores para man-db (2.10.2-1) ...

Procesando disparadores para kali-menu (2022.3.1) ...

Scanning processes...                                                                                          

Scanning processor microcode...                                                                                

Scanning linux images...                                                                                       

  

Running kernel seems to be up-to-date.

  

The processor microcode seems to be up-to-date.

  

No services need to be restarted.

  

No containers need to be restarted.

  

No user sessions are running outdated binaries.

  

No VM guests are running outdated hypervisor (qemu) binaries on this host.


```
al darle un pngcheck al archivo nos dice que tenemos problemas con los chunck, los cuales debemos cambiar ya que nos menciona que es demasiado grande.

```amcdanymx:Descargas/ $ pngcheck -v mystery                                                          [12:41:24]

File: mystery (202940 bytes)

  chunk IHDR at offset 0x0000c, length 13

1642 x 1095 image, 24-bit RGB, non-interlaced

  chunk sRGB at offset 0x00025, length 1

rendering intent = perceptual

  chunk gAMA at offset 0x00032, length 4: 0.45455

  chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter

  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)

ERRORS DETECTED in mystery

amcdanymx:Descargas/ $ hexeditor mystery                                                            [12:42:23]

(ristretto:3342): GdkPixbuf-CRITICAL **: 12:43:17.509: gdk_pixbuf_loader_close: assertion 'GDK_IS_PIXBUF_LOADER (loader)' failed

amcdanymx:Descargas/ $ file mystery                                                                 [12:43:17]

mystery: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced

amcdanymx:Descargas/ $ open mystery                                                                 [12:43:37]

amcdanymx:Descargas/ $ pngcheck -v mystery                                                          [12:43:41]

File: mystery (202940 bytes)

  chunk IHDR at offset 0x0000c, length 13

1642 x 1095 image, 24-bit RGB, non-interlaced

  chunk sRGB at offset 0x00025, length 1

rendering intent = perceptual

  chunk gAMA at offset 0x00032, length 4: 0.45455

  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)

:  invalid chunk length (too large)

ERRORS DETECTED in mystery

amcdanymx:Descargas/ $ hexeditor mystery                                                            [12:43:50]

(ristretto:3342): GdkPixbuf-CRITICAL **: 12:45:13.830: gdk_pixbuf_loader_close: assertion 'GDK_IS_PIXBUF_LOADER (loader)' failed

  

(ristretto:4284): GdkPixbuf-CRITICAL **: 12:45:13.831: gdk_pixbuf_loader_close: assertion 'GDK_IS_PIXBUF_LOADER (loader)' failed

amcdanymx:Descargas/ $ pngcheck -v mystery                                                          [12:45:13]

File: mystery (202940 bytes)

  chunk IHDR at offset 0x0000c, length 13

1642 x 1095 image, 24-bit RGB, non-interlaced

  chunk sRGB at offset 0x00025, length 1

rendering intent = perceptual

  chunk gAMA at offset 0x00032, length 4: 0.45455

  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)

:  invalid chunk length (too large)

ERRORS DETECTED in mystery

amcdanymx:Descargas/ $ hexeditor mystery                                                            [12:45:15]

amcdanymx:Descargas/ $ pngcheck -v mystery                                                          [12:46:23]

File: mystery (202940 bytes)

  chunk IHDR at offset 0x0000c, length 13

1642 x 1095 image, 24-bit RGB, non-interlaced

  chunk sRGB at offset 0x00025, length 1

rendering intent = perceptual

  chunk gAMA at offset 0x00032, length 4: 0.45455

  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)

  chunk IDAT at offset 0x00057, length 65445

zlib: deflated, 32K window, fast compression

  chunk IDAT at offset 0x10008, length 65524

  chunk IDAT at offset 0x20008, length 65524

  chunk IDAT at offset 0x30008, length 6304

  chunk IEND at offset 0x318b4, length 0

No errors detected in mystery (9 chunks, 96.3% compression).

amcdanymx:Descargas/ $ open mystery**



```


y al corregir y abrir el archivo obtenemos la bandera:

picoCTF{c0rrupt10n_1847995}
