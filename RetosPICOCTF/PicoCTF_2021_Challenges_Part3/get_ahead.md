# USERNAME -> amcdanymx

# GET aHEAD


## Description

Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:28916/](http://mercury.picoctf.net:28916/)

## Pistas

- Maybe you have more than 2 choices
- Check out tools like Burpsuite to modify your requests and look at the responses


## Solución
Ingresamos a la página que se nos proporciona, vemos que hay dos botones que cambia el fondo al color azul o rojo.
Se pueden utilizar el metodo get o el método post en consola, usando los siguientes parametros:

```

mx@kali ~

$ curl -X GET http://mercury.picoctf.net:28916/                    
<!doctype html>

<html>

<head>

<title>Red</title>

<link rel="stylesheet" type="text/css" href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css">

     <style>body {background-color: red;}</style>

</head>

     <body>

             <div class="container">

                     <div class="row">

                             <div class="col-md-6">

                                     <div class="panel panel-primary" style="margin-top:50px">

                                             <div class="panel-heading">

                                                     <h3 class="panel-title" style="color:red">Red</h3>

                                             </div>

                                             <div class="panel-body">

                                                     <form action="index.php" method="GET">

                                                             <input type="submit" value="Choose Red"/>

                                                     </form>

                                             </div>

                                     </div>

                             </div>

                             <div class="col-md-6">

                                     <div class="panel panel-primary" style="margin-top:50px">

                                             <div class="panel-heading">

                                                     <h3 class="panel-title" style="color:blue">Blue</h3>

                                             </div>

                                             <div class="panel-body">

                                                     <form action="index.php" method="POST">

                                                             <input type="submit" value="Choose Blue"/>

                                                     </form>

                                             </div>

                                     </div>

                             </div>

                     </div>

             </div>

     </body>

</html>

  
```

```
amcdanymx@kali ~

$ curl -X POST http://mercury.picoctf.net:28916/                         
<!doctype html>

<html>

<head>

<title>Blue</title>

<link rel="stylesheet" type="text/css" href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css">

     <style>body {background-color: blue;}</style>

</head>

     <body>

             <div class="container">

                     <div class="row">

                             <div class="col-md-6">

                                     <div class="panel panel-primary" style="margin-top:50px">

                                             <div class="panel-heading">

                                                     <h3 class="panel-title" style="color:red">Red</h3>

                                             </div>

                                             <div class="panel-body">

                                                     <form action="index.php" method="GET">

                                                             <input type="submit" value="Choose Red"/>

                                                     </form>

                                             </div>

                                     </div>

                             </div>

                             <div class="col-md-6">

                                     <div class="panel panel-primary" style="margin-top:50px">

                                             <div class="panel-heading">

                                                     <h3 class="panel-title" style="color:blue">Blue</h3>

                                             </div>

                                             <div class="panel-body">

                                                     <form action="index.php" method="POST">

                                                             <input type="submit" value="Choose Blue"/>

                                                     </form>

                                             </div>

                                     </div>

                             </div>

                     </div>

             </div>

     </body>

</html>
```

Lo que hicimos con las llamadas en consola con get y post estamos simulando los botones que nos aparecen en la página, rojo o azul.
Si usamos el metodo head lo invocamos con -i y en este caso obtenemos la respuesta:

```
amcdanymx@kali ~

$ curl -I HEAD  http://mercury.picoctf.net:28916/                                [19:21:24]

curl: (6) Could not resolve host: HEAD

HTTP/1.1 200 OK

flag: picoCTF{r3j3ct_th3_du4l1ty_70bc61c4}

Content-type: text/html; charset=UTF-8
```
  
