# USERNAME -> amcdanymx


#### Descripción

I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/c00c449c3b08daaccacca6f9d5c55d49/Forensics%20is%20fun.pptm)

#### Pistas

No hay 

#### Solución

Descargamos el archivo que nos da el reto, vemos que es un archivo de tipo powerpoint el cual viene comprimido, lo desempaquetamos y posteriormente revisamos el contenido.

Podemos ver que hay  varios archivos con otras extensiones por lo que nos es conveniente revisarlos con más detalle desde un editor de texto, para eso abrimos VSCode, en el encontramos unn archivo llamado "Hidden" que es interesante porque solo nos muestra una cadena encriptada.

Usamos la consola para desencriptar la cadena en base64 :

```
**macrohardweakedge ➤ ls                                                                                        

'[Content_Types].xml'   docProps  'Forensics is fun.pptm'   ppt   _rels

macrohardweakedge ➤ ls -la                                                                                    

total 132

drwxr-xr-x  5 amcdanymx amcdanymx   4096 nov  3 19:06  .

drwxr-xr-x 11 amcdanymx amcdanymx   4096 nov  3 19:04  ..

-rw-r--r--  1 amcdanymx amcdanymx  10660 ene  1  1980 '[Content_Types].xml'

drwxr-xr-x  2 amcdanymx amcdanymx   4096 nov  3 19:06  docProps

-rw-r--r--  1 amcdanymx amcdanymx 100093 mar 23  2021 'Forensics is fun.pptm'

drwxr-xr-x  7 amcdanymx amcdanymx   4096 nov  3 19:06  ppt

drwxr-xr-x  2 amcdanymx amcdanymx   4096 nov  3 19:06  _rels

macrohardweakedge ➤ grep -R pico                                                                              

macrohardweakedge ➤ code .                                                                                    

macrohardweakedge ➤ echo "Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q" | tr -d " "

ZmxhZzogcGljb0NURntEMWRfdV9rbjB3X3BwdHNfcl96MXA1fQ

macrohardweakedge ➤ echo "Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q" | tr -d " "  | base64 -d

```

Y encontramos la bandera:

```
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: entrada inválida
```
