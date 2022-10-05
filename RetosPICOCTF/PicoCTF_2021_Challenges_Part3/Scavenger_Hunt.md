# USERNAME -> amcdanymx

# Scavenger Hunt


## Description

There is some interesting information hidden around this site [http://mercury.picoctf.net:55079/](http://mercury.picoctf.net:55079/). Can you find it?

## Pistas

- You should have enough hints to find the files, don't run a brute forcer.

## Solución
Ingresamos al sittio web, la pista nos dice que no hay que hacer un ataque de fuerza bruta, vemos que el sitio nos dice que se hizo con las tecnologías de HTML, CSS y JS, vamos a inspeccionar esos códigos

HTML

```
<!doctype html>

<html>

<head>

<title>Scavenger Hunt</title>

<link href="[https://fonts.googleapis.com/css?family=Open+Sans|Roboto](https://fonts.googleapis.com/css?family=Open+Sans|Roboto)" rel="stylesheet">

<link rel="stylesheet" type="text/css" href="[mycss.css](http://mercury.picoctf.net:55079/mycss.css)">

<script type="application/javascript" src="[myjs.js](http://mercury.picoctf.net:55079/myjs.js)"></script>
</head>
<body>
<div class="container">
<header>
<h1>Just some boring HTML</h1>
</header>

<button class="tablink" onclick="openTab('tabintro', this, '#222')" id="defaultOpen">How</button>

<button class="tablink" onclick="openTab('tababout', this, '#222')">What</button>

  
<div id="tabintro" class="tabcontent">
<h3>How</h3>
<p>How do you like my website?</p>
</div>
<div id="tababout" class="tabcontent">

<h3>What</h3>

<p>I used these to make this site: <br/>

HTML <br/>

CSS <br/>

JS (JavaScript)

</p>

<!-- Here's the first part of the flag: picoCTF{t -->

</div>

  

</div>

  

</body>

</html>

```

Se nos da la primera parte de la bandera en el archivo HTML

```

picoCTF{t

```

Vemos que hay dos archivos más, analizando el archivo JS no contiene nada sobre la bandera pero nos menciona algo para inspeccionar más adelante el archivo robots.txt

por ahora vemos el archivo .css que corresponde a la hoja de estilos y encontramos lo siguiente:

```
div.container {
    width: 100%;
}

header {
    background-color: black;
    padding: 1em;
    color: white;
    clear: left;
    text-align: center;
}

body {
    font-family: Roboto;
}

h1 {
    color: white;
}

p {
    font-family: "Open Sans";
}

.tablink {
    background-color: #555;
    color: white;
    float: left;
    border: none;
    outline: none;
    cursor: pointer;
    padding: 14px 16px;
    font-size: 17px;
    width: 50%;
}

.tablink:hover {
    background-color: #777;
}

.tabcontent {
    color: #111;
    display: none;
    padding: 50px;
    text-align: center;
}

#tabintro { background-color: #ccc; }
#tababout { background-color: #ccc; }

/* CSS makes the page look nice, and yes, it also has part of the flag. Here's part 2: h4ts_4_l0 */

```

Al final nos dan la segunda parte de la bandera:
```
h4ts_4_l0

```

Vamos a revisar el archivo robots del sitio web ingresando de la siguiente manera:

```
http://mercury.picoctf.net:55079/robots.txt

```

Nos encontramos con lo siguiente:

```
User-agent: *
Disallow: /index.html
# Part 3: t_0f_pl4c
# I think this is an apache server... can you Access the next flag?

```

se nos da la tercera parte de la bandera
```
t_0f_pl4c

```

Armando por ahora la bandera nos queda algo como esto:

```

picoCTF{th4ts_4_l0t_0f_pl4c



```

Se nos menciona en el archivo robots que es yun servidor apache, vamos a ver si podemos entrar al archivo:


```
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.

```

Efectivamente pudimos entrar a ese archivo que comunmente no es accesible, nos da otra pista para la bandera, nos menciona que puede almacenarm mucha información, en los dispositios mac cuando compilas un sitio web almacenas archivos de Mac en archivos con extensión .DS_Store, vamos a buscarlo:


```

Congrats! You completed the scavenger hunt. Part 5: _74cceb07}

```

Y ese fue el último paso y la última parte de la bandera, completandola nos queda lo siguiente:


```
picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_74cceb07}

```
