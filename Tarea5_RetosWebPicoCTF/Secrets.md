# USERNAME -> amcdanymx

# Secrets

## Description

We have several pages hidden. Can you find the one with the flag?The website is running [here](http://saturn.picoctf.net:49917/).


## Pistas

- folders folders folders

## Solución

Viendo el archivo HTML, vemos que hay una carpeta que esta oculta pero aparece especificada en el HTML, llamada secret

```
<!DOCTYPE html>

<html>

<head>

<meta charset="UTF-8" />

<meta

name="viewport"

content="width=device-width, initial-scale=1, shrink-to-fit=no"

/>

<meta name="description" content="" />

<!-- Bootstrap core CSS -->

<link href="[vendor/bootstrap/css/bootstrap.min.css](http://saturn.picoctf.net:49917/vendor/bootstrap/css/bootstrap.min.css)" rel="stylesheet" />

<!-- title -->

<title>home</title>

<!-- css -->

<link href="[secret/assets/index.css](http://saturn.picoctf.net:49917/secret/assets/index.css)" rel="stylesheet" />

</head>

<body>

<!-- ***** Header Area Start ***** -->

<div class="topnav">

<a class="active" href="[#home](http://saturn.picoctf.net:49917/#home)">Home</a>

<a href="[about.html](http://saturn.picoctf.net:49917/about.html)">About</a>

<a href="[contact.html](http://saturn.picoctf.net:49917/contact.html)">Contact</a>

</div>

  

<div class="imgcontainer">

<img

src="[secret/assets/DX1KYM.jpg](http://saturn.picoctf.net:49917/secret/assets/DX1KYM.jpg)"

alt="https://www.alamy.com/security-safety-word-cloud-concept-image-image67649784.html"

class="responsive"

/>

<div class="top-left">

<h1>If security wasn't your job, would you do it as a hobby?</h1>

</div>

</div>

</body>

</html>

```

Al moverme a la carpeta encontramos lo siguiente

```
http://saturn.picoctf.net:49917/secret/

# Finally. You almost found me. you are doing well

```

Vemos que es otro index, por lo cual podemos revisar el código fuente de la página, 

```
  

<!DOCTYPE html>

<html>

<head>

<title></title>

<link rel="stylesheet" href="[hidden/file.css](http://saturn.picoctf.net:49917/secret/hidden/file.css)" />

</head>

  

<body>

<h1>Finally. You almost found me. you are doing well</h1>

<img src="[https://media1.tenor.com/images/0a6aff9f825af62c05adfbd75039cc7b/tenor.gif?itemid=4648337](https://media1.tenor.com/images/0a6aff9f825af62c05adfbd75039cc7b/tenor.gif?itemid=4648337)" alt="Something Like That GIF - Andy Parksandrecreation Wtf GIFs" style="max-width: 833px; background-color: rgb(151, 121, 85);" width="833" height="937.125">

</body>

</html>

```

Podemos ver que también hay una carpeta llamada Hidden, nos movemos a ella especificando la ruta 

saturn.picoctf.net:49917/secret/hidden



```

saturn.picoctf.net:49917/secret/hidden


```
Ahí vemos que dentro de la inspeccion de código hay una carpeta llamada /superhidden, nos movemos a ella


```
saturn.picoctf.net:49917/secret/hidden/superhidden
```


Y es aquí en la carpeta superhidden donde encontramos la bandera:
```
Finally. You found me. But can you see mee

*Hacemos una seleccion en la página para encontrar el texto*

picoCTF{succ3ss_@h3n1c@10n_790d2615}

```


