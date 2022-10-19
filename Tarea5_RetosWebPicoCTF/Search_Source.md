# USERNAME -> amcdanymx

# Search Source


## Description

The developer of this website mistakenly left an important artifact in the website source, can you find it?The website is [here](http://saturn.picoctf.net:61941/)

## Pistas

- How could you mirror the website on your local machine so you could use more powerful tools for searching?


## Solución

En este reto basicamente tenemos que insperccionar el sitio, en mi caso me fue más sencillo revisar todos los archivos del código, hay muchos archivos cde scripts js, pero al inicio tenemos los clasicos de hoja de estilos, encontré la bandera en el main de css, llamado styles.css
```
    
/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_8de925a7} **/
 .carousel-indicators li {
     width: 20px;
     height: 20px;
     border-radius: 11px;
     background-color: #070000;
}

```

En esta instrucción para ser precisos.