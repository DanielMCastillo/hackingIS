# USERNAME -> amcdanymx

## So Meta

#### Description

#### Description

Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/89b371a46702a31aa9931a2a2b12f8bf/pico_img.png).


  
#### PISTAS
- What does meta mean in the context of files?
- Ever heard of metadata?


#### SOLUCIÓN

Descargamos la imagen que se nos da mediante el enlace, la metememos en una carpeta de nuestra preferencia, utilizamos una herramienta llamada exitfool para revisar la infromación de un archivo, en este caso aplicamos para nuestra imagen que se descargó, podemos ver que en el campo de "Artist" de los datos generales se encuentra la bandera:

La bandera es: 
```

amcdanymx@kali:~/picoCTF/forensic/someta % exiftool pico_img.png

ExifTool Version Number     : 12.44

File Name                   : pico_img.png

Directory                   : .

File Size                   : 109 kB

File Modification Date/Time : 2022:10:10 17:39:04-05:00

File Access Date/Time       : 2022:10:10 17:39:41-05:00

File Inode Change Date/Time : 2022:10:10 17:39:41-05:00

File Permissions            : -rw-r--r--

File Type                   : PNG

File Type Extension         : png

MIME Type                   : image/png

Image Width                 : 600

Image Height                : 600

Bit Depth                   : 8

Color Type                  : RGB

Compression                 : Deflate/Inflate

Filter                      : Adaptive

Interlace                   : Noninterlaced

Software                    : Adobe ImageReady

XMP Toolkit                 : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27

Creator Tool                : Adobe Photoshop CS6 (Windows)

Instance ID                 : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B

Document ID                 : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B

Derived From Instance ID    : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B

Derived From Document ID    : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B

Warning                     : [minor] Text/EXIF chunk(s) found after PNG IDAT (may be ignored by some readers)

Artist                      : picoCTF{s0_m3ta_eb36bf44}

Image Size                  : 600x600

Megapixels                  : 0.360

amcdanymx@kali:~/picoCTF/forensic/someta %

  
  
**



```