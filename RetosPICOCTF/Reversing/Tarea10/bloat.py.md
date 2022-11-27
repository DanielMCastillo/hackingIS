# USERNAME -> amcdanymx

#### Description

Can you get the flag?Run this [Python program](https://artifacts.picoctf.net/c/430/bloat.flag.py) in the same directory as this [encrypted flag](https://artifacts.picoctf.net/c/430/flag.txt.enc).

#### PISTAS
- None

#### SOLUCIÓN

En este desafío nos dan un archivo ccon extensión .py y un archivo con la bandera encriptada, analizando el código como en el reto anterior nos encontramos con varias funciones y condiciones donde se encripta la bandera, aquí solo fui probando y encontré una instrucción llamada sys.exit(0), solo camenté dicha instrucción y encontramos la badnera:
```  

else:

   print(a[51]+a[71]+a[64]+a[83]+a[94]+a[79]+a[64]+a[82]+a[82]+a[86]+a[78]+\

a[81]+a[67]+a[94]+a[72]+a[82]+a[94]+a[72]+a[77]+a[66]+a[78]+a[81]+\

a[81]+a[68]+a[66]+a[83])

   #sys.exit(0)

   return False**

```

Nuevamente ejecutamos el código junto al archivo de la bandera encriptada
```


amcdanymx:bloat/ $ python bloat.flag.py ./flag.txt.enc                  
Please enter correct password for flag: holaprueba

That password is incorrect

amcdanymx:bloat/ $ code bloat.flag.py                                   

amcdanymx:bloat/ $ python bloat.flag.py ./flag.txt.enc                  

Please enter correct password for flag: hoka

That password is incorrect

Welcome back... your flag, user:

picoCTF{d30bfu5c4710n_f7w_5e14b257}

amcdanymx:bloat/ $      

```

y obtenemos la bandera: picoCTF{d30bfu5c4710n_f7w_5e14b257}


