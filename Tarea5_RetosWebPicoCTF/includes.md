# USERNAME -> amcdanymx

# Includes


## Description


Can you get the flag?Go to this [website](http://saturn.picoctf.net:57833/) and see what you can discover.

## Pistas

- Is there more code than what the inspector initially shows?


## Solución

Como hemos echo en otros desafíos, entramos al siito web mediante el link, podemos ver que hay algunos parrafos de texto y un botón, pasamos a examinar más a profunidad el sitio, viendo el código fuente...

```
  

<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<meta http-equiv="X-UA-Compatible" content="ie=edge">

<link rel="stylesheet" href="[style.css](http://saturn.picoctf.net:57833/style.css)">

<title>On Includes</title>

</head>

<body>

<script src="[script.js](http://saturn.picoctf.net:57833/script.js)"></script>

<h1>On Includes</h1>

<p>Many programming languages and other computer files have a directive,

often called include (sometimes copy or import), that causes the

contents of a second file to be inserted into the original file. These

included files are called copybooks or header files. They are often used

to define the physical layout of program data, pieces of procedural code

and/or forward declarations while promoting encapsulation and the reuse

of code.</p>

<br>

<p> Source: Wikipedia on Include directive </p>

<button type="button" onclick="greetings();">Say hello</button>

</body>

</html>

```

Nuevamente vemos que el archivo html tiene ligados otros archivos que corresponden al css hoja de estilos y un archivo js

Inspeccionamos el archivo .css

```
body {
  background-color: lightblue;
}

/*  picoCTF{1nclu51v17y_1of2_  */

```

Solo contiene un par de líneas, entre ellas la primera parte de la bandera, pasasmos a ver el archivo .js


```

function greetings()
{
  alert("This code is in a separate file!");
}

//  f7w_2of2_b8f4b022}

```

Contiene la funcionalidad del botón que se encuntra en la página web, y la segunda parte de la bandera, armamos la bandera

```

picoCTF{1nclu51v17y_1of2_f7w_2of2_b8f4b022}


```

