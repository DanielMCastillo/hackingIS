# USERNAME -> amcdanymx

## Instrucciones 

Al entrar a la página en picoCTF tenemos la descripción del desafío de insp3ct0r
Se nos da un link el cuál nos lleva a una página web

![[Pasted image 20220922182411.png]]

- En la parte inferior aparece la opción para subir la solución de la bandera que tenemos que entregar para poder completar el desafío. 

## Web
En la página web podemos revisar que hay dos pestañas y para "inspeccionar" debemos de hacer lo siguiente:

- Damos click derecho y seleccionamos la opción de "Código fuente de la página"

![[Pasted image 20220922182356.png]]

## 1/3

Al irnos al código fuente encontramos la estructura general de la página, podemos ver los archivos HTML, CSS, y JS del sitio web, en cada uno de estos archivos podremos encontrar una parte de la bandera, en ester caso primero vemos el código HTML hasta el final nos aparece la primera parte de la bandera 1/3

```
<!doctype html>
<html>
<head>
<title>My First Website :)</title>
<link href="[https://fonts.googleapis.com/css?family=Open+Sans|Roboto](https://fonts.googleapis.com/css?family=Open+Sans|Roboto)" rel="stylesheet">

<link rel="stylesheet" type="text/css" href="[mycss.css](https://jupiter.challenges.picoctf.org/problem/44924/mycss.css)">

<script type="application/javascript" src="[myjs.js](https://jupiter.challenges.picoctf.org/problem/44924/myjs.js)"></script>

</head>

  
<body>
<div class="container">
<header>
<h1>Inspect Me</h1>
</header>
<button class="tablink" onclick="openTab('tabintro', this, '#222')" id="defaultOpen">What</button>
<button class="tablink" onclick="openTab('tababout', this, '#222')">How</button>
<div id="tabintro" class="tabcontent">
<h3>What</h3>
<p>I made a website</p>
</div>
<div id="tababout" class="tabcontent">
<h3>How</h3>
<p>I used these to make this site: <br/>
HTML <br/>
CSS <br/>
JS (JavaScript)
</p>
<!-- Html is neat. Anyways have 1/3 of the flag: picoCTF{tru3_d3 -->
</div>
</div>
</body>
</html>
```

## 2/3
En el archivo de estilos CSS podremos encontrar la segunda parte de la bandera 2/3
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

/* You need CSS to make pretty pages. Here's part 2/3 of the flag: t3ct1ve_0r_ju5t */
```

## 3/3
Finalmente en el archivo JS podremos encontrar la tercera parte de la bandea 3/3
```
function openTab(tabName,elmnt,color) {
    var i, tabcontent, tablinks;
    tabcontent = document.getElementsByClassName("tabcontent");
    for (i = 0; i < tabcontent.length; i++) {
	tabcontent[i].style.display = "none";
    }
    tablinks = document.getElementsByClassName("tablink");
    for (i = 0; i < tablinks.length; i++) {
	tablinks[i].style.backgroundColor = "";
    }
    document.getElementById(tabName).style.display = "block";
    if(elmnt.style != null) {
	elmnt.style.backgroundColor = color;
    }
}

window.onload = function() {
    openTab('tabintro', this, '#222');
}

/* Javascript sure is neat. Anyways part 3/3 of the flag: _lucky?f10be399} */
```

