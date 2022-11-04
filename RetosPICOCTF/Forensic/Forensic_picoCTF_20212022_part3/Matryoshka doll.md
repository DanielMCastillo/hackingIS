# USERNAME -> amcdanymx


#### Descripción

Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/1b70cffdd2f05427fff97d13c496963f/dolls.jpg)

#### Pistas

- Wait, you can hide files inside files? But how do you find them?
- Make sure to submit the flag as picoCTF{XXXXX}


#### Solución

Utilizamos la herramienta de binwalk para leer los datos del archivo, con el comando binwalk -3 "nombre de archivo" nos da sus datos en decimal y hexadecimal, vemos que al leer el archivo aparecen dos carpetas, nos movemos entre ellas y vemos otro archivo de imagen, tall como son este tipo de muñecas, dentro de una hay otra, repetimos el proceso hasta que encontremos algo diferente.



```
**

amcdanymx@kali:~/picoCTF/matryoshkadoll $ binwalk dolls.jpg
DECIMAL   HEXADECIMAL DESCRIPTION

--------------------------------------------------------------------------------

0         0x0         PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced

3226      0xC9A       TIFF image data, big-endian, offset of first image directory: 8

272492    0x4286C     Zip archive data, at least v2.0 to extract, compressed size: 378954, uncompressed size: 383938, name: base_images/2_c.jpg

651612    0x9F15C     End of Zip archive, footer length: 22

  

amcdanymx@kali:~/picoCTF/matryoshkadoll $ binwalk -e dolls.jpg

  

DECIMAL   HEXADECIMAL DESCRIPTION

--------------------------------------------------------------------------------

0         0x0         PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced

3226      0xC9A       TIFF image data, big-endian, offset of first image directory: 8

272492    0x4286C     Zip archive data, at least v2.0 to extract, compressed size: 378954, uncompressed size: 383938, name: base_images/2_c.jpg

651612    0x9F15C     End of Zip archive, footer length: 22

  

amcdanymx@kali:~/picoCTF/matryoshkadoll $ ls

dolls.jpg  _dolls.jpg.extracted

amcdanymx@kali:~/picoCTF/matryoshkadoll $ cd _dolls.jpg.extracted

amcdanymx@kali:~/picoCTF/matryoshkadoll/_dolls.jpg.extracted $ ls

4286C.zip  base_images

amcdanymx@kali:~/picoCTF/matryoshkadoll/_dolls.jpg.extracted $ cd base_images

amcdanymx@kali:~/picoCTF/matryoshkadoll/_dolls.jpg.extracted/base_images $ ls

2_c.jpg

amcdanymx@kali:~/picoCTF/matryoshkadoll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images $ binwalk 4_c.jpg                                                                      127

amcdanymx@kali:~/picoCTF/matryoshkadoll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images $ ls

4_c.jpg  _4_c.jpg.extracted

amcdanymx@kali:~/picoCTF/matryoshkadoll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images $ cd _4_c.jpg.extracted

amcdanymx@kali:~/picoCTF/matryoshkadoll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted $ ls

136DA.zip  flag.txt

amcdanymx@kali:~/picoCTF/matryoshkadoll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted $ cat flag.txt
**
```

Se repitió el proceso hasta la imagen 4, que es la final y nos da un archivo con la extensión .txt

- Leemos el archivo 

```

amcdanymx@kali:~/picoCTF/matryoshkadoll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images $ binwalk 4_c.jpg                                                                      127

amcdanymx@kali:~/picoCTF/matryoshkadoll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images $ ls

4_c.jpg  _4_c.jpg.extracted

amcdanymx@kali:~/picoCTF/matryoshkadoll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images $ cd _4_c.jpg.extracted

amcdanymx@kali:~/picoCTF/matryoshkadoll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted $ ls

136DA.zip  flag.txt

amcdanymx@kali:~/picoCTF/matryoshkadoll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted $ cat flag.txt

```


y obtenemos la bandera
```
picoCTF{bf6acf878dcbd752f4721e41b1b1b66b}

```