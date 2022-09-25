# USERNAME picoCTF -> amcdanymx

# convertme.py

## Descripción
Ejecute el script de Python y convierta el número dado de decimal a binario para obtener la bandera.
Descargar secuencia de comandos Python
[Download Python script](https://artifacts.picoctf.net/c/31/convertme.py)

## Pistas

¡Busque una aplicación de conversión de números decimales a binarios en la web o use la calculadora de su computadora!

La función str_xor no necesita ingeniería inversa para este desafío

Si tiene Python en su computadora, puede descargar el script normalmente y ejecutarlo. De lo contrario, use el comando wget en el webshell.

Para usar wget en el shell web, primero haga clic derecho en el enlace de descarga y seleccione 'Copiar enlace' o 'Copiar dirección de enlace'

Escriba todo después del signo de dólar en el shell web: $ wget , luego pegue el enlace después del espacio después de wget y presione enter. ¡Esto descargará el script para usted en el webshell para que pueda ejecutarlo!

Finalmente, para ejecutar el script, escriba todo después del signo de dólar y luego presione enter: $ python3 convertme.py
## Solución 

- Descargamos el archivo
- Ejecutamos en consola 
- Convertimos a base lo que se nos pida con alguna herramienta, yo utilizo esta
https://www.rapidtables.com/convert/number/decimal-to-binary.html

```
ls
python convertme.py


┌──(amcdanymx@kali)-[~/Descargas]

└─$ python convertme.py

If 29 is in decimal base, what is it in binary base?
Answer: 11101
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_9c3b7d4d}

```
