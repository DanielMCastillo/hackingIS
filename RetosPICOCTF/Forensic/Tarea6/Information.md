
# USERNAME -> amcdanymx


#### Description

  Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/149ab4b27d16922142a1e8381677d76f/cat.jpg)
  
#### PISTAS
- Look at the details of the file
- Make sure to submit the flag as picoCTF{XXXXX}

#### SOLUCIÓN

Descargamos el archivo, utilizamos la herramienta de exiftool para ver los detalles del archivo, revisamos después con License donde vemos que está codificado en base 64, decodificamos y obtenemos la bandera:

```
**  
  

% ls

cat.jpg

% file cat.jpg  

cat.jpg: JPEG image data, JFIF standard 1.02, aspect ratio, density 1x1, segment length 16, baseline, precision 8, 2560x1598, components 3

% exiftool cat.jpg

ExifTool Version Number     : 12.44

File Name                   : cat.jpg

Directory                   : .

File Size                   : 878 kB

File Modification Date/Time : 2021:03:15 12:24:46-06:00

File Access Date/Time       : 2022:11:07 12:53:09-06:00

File Inode Change Date/Time : 2022:11:07 12:52:57-06:00

File Permissions            : -rw-r--r--

File Type                   : JPEG

File Type Extension         : jpg

MIME Type                   : image/jpeg

JFIF Version                : 1.02

Resolution Unit             : None

X Resolution                : 1

Y Resolution                : 1

Current IPTC Digest         : 7a78f3d9cfb1ce42ab5a3aa30573d617

Copyright Notice            : PicoCTF

Application Record Version  : 4

XMP Toolkit                 : Image::ExifTool 10.80

License                     : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9

Rights                      : PicoCTF

Image Width                 : 2560

Image Height                : 1598

Encoding Process            : Baseline DCT, Huffman coding

Bits Per Sample             : 8

Color Components            : 3

Y Cb Cr Sub Sampling        : YCbCr4:2:0 (2 2)

Image Size                  : 2560x1598

Megapixels                  : 4.1

% exiftool cat.jpg | grep License

License                     : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9

% exiftool cat.jpg | grep License | sed -e 's./.*: //'

sed: -e expresión #1, carácter 9: orden `s' sin terminar

% exiftool cat.jpg | grep License | sed -e 's/.*: //'

cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9

% exiftool cat.jpg | grep License | sed -e 's/.*: //' | base64 -d

picoCTF{the_m3tadata_1s_modified}%                                         
```


```
picoCTF{the_m3tadata_1s_modified}                                                                          
```

