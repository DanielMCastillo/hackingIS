# USERNAME -> amcdanymx

# Local Autorithy


## Description

Can you get the flag?Go to this [website](http://saturn.picoctf.net:55826/) and see what you can discover.

## Pistas

How is the password checked on this website?


## Solución

Vemos que en archivo HTML hay dos archivos especificados directa o indirectamente, buscando en el css no encontré nada pero si vamos a uno que es sobre la pista y la autentiuficación encontramos el archivo de login.php

```
<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<meta http-equiv="X-UA-Compatible" content="ie=edge">

<link rel="stylesheet" href="[style.css](http://saturn.picoctf.net:55826/style.css)">

<title>Secure Customer Portal</title>

</head>

<body>

  

<h1>Secure Customer Portal</h1>

<p>Only letters and numbers allowed for username and password.</p>

<form role="form" action="login.php" method="post">

<input type="text" name="username" placeholder="Username" required

autofocus></br>

<input type="password" name="password" placeholder="Password" required>

<button type="submit" name="login">Login</button>

</form>

</body>

</html>

```

```
<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<meta http-equiv="X-UA-Compatible" content="ie=edge">

<link rel="stylesheet" href="[style.css](http://saturn.picoctf.net:55826/style.css)">

<title>Login Page</title>

</head>

<body>

<script src="[secure.js](http://saturn.picoctf.net:55826/secure.js)"></script>

<p id='msg'></p>

<form hidden action="admin.php" method="post" id="hiddenAdminForm">

<input type="text" name="hash" required id="adminFormHash">

</form>

<script type="text/javascript">

function filter(string) {

filterPassed = true;

for (let i =0; i < string.length; i++){

cc = string.charCodeAt(i);

if ( (cc >= 48 && cc <= 57) ||

(cc >= 65 && cc <= 90) ||

(cc >= 97 && cc <= 122) )

{

filterPassed = true;

}

else

{

return false;

}

}

return true;

}

window.username = "";

window.password = "";

usernameFilterPassed = filter(window.username);

passwordFilterPassed = filter(window.password);

if ( usernameFilterPassed && passwordFilterPassed ) {

loggedIn = checkPassword(window.username, window.password);

if(loggedIn)

{

document.getElementById('msg').innerHTML = "Log In Successful";

document.getElementById('adminFormHash').value = "2196812e91c29df34f5e217cfd639881";

document.getElementById('hiddenAdminForm').submit();

}

else

{

document.getElementById('msg').innerHTML = "Log In Failed";

}

}

else {

document.getElementById('msg').innerHTML = "Illegal character in username or password."

}

</script>

</body>

</html>


```

En este archivo encontramos más información sobre el sitio entre lo que encontramos un script de .js llamado secure.js, lo examinamos y enonctramos lo siguieente:

```

  
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}

```

Básicamente nos dan las credenciales para ingresar al sitio web, donde encontrasmos admin y password
Los ponemos en los campos del sitio para encontrar la bandera:

```

picoCTF{j5_15_7r4n5p4r3n7_b0c2c9cb}

```