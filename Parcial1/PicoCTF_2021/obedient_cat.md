# USERNAME picoCTF -> amcdanymx
# Obedient cat

## Desafío
Este archivo tiene una bandera a plena vista (también conocida como "claro"). [Descargar bandera](https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag).

## Pistas
Cualquier sugerencia sobre cómo ingresar un comando en la Terminal (como la siguiente), comenzará con un '$'... todo lo que esté después del signo de dólar se escribirá (o copiará y pegará) en su Terminal.

Para acceder al archivo en su shell, ingrese lo siguiente en el indicador de Terminal: $ wget https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag 

man cat 

## Solución
- Descargamos el archivo que nos dan en el link
- corremos el siguiente comando para leerlo

```
cat flag
picoCTF{s4n1ty_v3r1f13d_4a2b35fd}
```

Como se nos mencionó el archivo tenía la bandera a plena vista, solo tenemos que leerlo. 