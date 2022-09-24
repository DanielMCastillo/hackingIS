## Description

# USERNAME -> amcdanymx


Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/29835/` ([link](https://jupiter.challenges.picoctf.org/problem/29835/)) or http://jupiter.challenges.picoctf.org:29835

*PISTA*
Never trust the client

- Entramos a la URL 
Vemos lo siguiente en el portal 
![[Pasted image 20220924130824.png]]

* Ingresamos holamundo como password de prueba, la verifica pero nos dice que es incorrecta
![[Pasted image 20220924130912.png]]

- Inspeccionamos el código fuente de la página 

```

<html>
<head>
<title>Secure Login Portal</title>
</head>
<body bgcolor=blue>
<!-- standard MD5 implementation -->
<script type="text/javascript" src="md5.js"></script>

<script type="text/javascript">
  function verify() {
    checkpass = document.getElementById("pass").value;
    split = 4;
    if (checkpass.substring(0, split) == 'pico') {
      if (checkpass.substring(split*6, split*7) == '723c') {
        if (checkpass.substring(split, split*2) == 'CTF{') {
         if (checkpass.substring(split*4, split*5) == 'ts_p') {
          if (checkpass.substring(split*3, split*4) == 'lien') {
            if (checkpass.substring(split*5, split*6) == 'lz_7') {
              if (checkpass.substring(split*2, split*3) == 'no_c') {
                if (checkpass.substring(split*7, split*8) == 'e}') {
                  alert("Password Verified")
                  }
                }
              }
      
            }
          }
        }
      }
    }
    else {
      alert("Incorrect password");
    }
    
  }
</script>
<div style="position:relative; padding:5px;top:50px; left:38%; width:350px; height:140px; background-color:yellow">
<div style="text-align:center">
<p>This is the secure login portal</p>
<p>Enter valid credentials to proceed</p>
<form action="index.html" method="post">
<input type="password" id="pass" size="8" />
<br/>
<input type="submit" value="verify" onclick="verify(); return false;" />
</form>
</div>
</div>
</body>
</html>

```


Parece que tenemos una función llamada verificar que verifica si la contraseña ingresada es correcta. Al leer la función línea por línea podemos obtener la contraseña

1- Primero obtenemos el valor insertado por el usuario en la variable checkpass, línea 11.

2- Luego de esto, le asignamos 4 a la variable split. linea 12

3- La primera declaración if verifica si las primeras 4 posiciones de la contraseña dada son "pico", si es así, pasa a la siguiente declaración if, línea 13.

4- El segundo if verifica si el valor en el intervalo entre las posiciones 24 a 28 (-1) es 706c, si es cierto pasa al siguiente if. línea 14.

5- El tercer if compara el intervalo entre las posiciones 4 a 8 (-1) a CTF{, si es cierto pasa al siguiente if. línea 15.

6- Y así sucesivamente, el proceso es muy similar al de todas las sentencias if.

Mientras leemos toda esta función podemos reconstruir la contraseña de la siguiente manera, en el paso 3 tenemos las primeras 4 posiciones: pico. En el paso 5 tenemos las siguientes cuatro posiciones: CTF

*Al final solo armamos la bandera*

```
picoCTF{no_clients_plz_7723ce}}

```
