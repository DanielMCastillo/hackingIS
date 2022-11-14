 USERNAME -> amcdanymx

#### Description

I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled2.png)



#### Pistas
- [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
- Think of different ways you can "stack" images
 
#### SOLUCIÓN

Descargamos las dos imagenes, en este desafío vamos a utilizar una herramienta que nos ayude a decifrar las imagenes ya que están en solo pixeles, la herrameinta es stegsolve que la encontramos en el repo https://github.com/zardus/ctf-tools/blob/master/stegsolve/install
Dicha herramienta nos permite combinar, hacer un XOR, AND o ADD de imagenes y así logramos decifrar la bandera
```
**  

opt ⌚ 19:20:53

$ wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar

stegsolve.jar: Permiso denegado

  

/opt ⌚ 19:20:57

$ sudo wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar

[sudo] contraseña para amcdanymx:

--2022-11-13 19:21:06--  http://www.caesum.com/handbook/Stegsolve.jar

Resolviendo www.caesum.com (www.caesum.com)... 216.234.173.1

Conectando con www.caesum.com (www.caesum.com)[216.234.173.1]:80... conectado.

Petición HTTP enviada, esperando respuesta... 200 OK

Longitud: 312271 (305K) [application/x-java-archive]

Grabando a: «stegsolve.jar»

  

stegsolve.jar            100%[==============================================>] 304.95K   165KB/s en 1.8s    

  

2022-11-13 19:21:09 (165 KB/s) - «stegsolve.jar» guardado [312271/312271]

```

En la herramienta combinamos las imagenes y obtenemos la bandera al añadir:

```
picoCTF{d562333d}

```