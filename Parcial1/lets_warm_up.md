# USERNAME picoCTF -> amcdanymx
# Let's warm up

## Desafío

Si te dijera que una palabra comienza con 0x70 en hexadecimal, ¿con qué comenzaría en ASCII?

## Pista

Envíe su respuesta en el formato de bandera de nuestra competencia. Por ejemplo, si su respuesta fue 'hola', enviaría 'picoCTF{hola}' como indicador.

## Solución

[RapidTables](https://www.rapidtables.com/convert/number/hex-to-ascii.html) es un buen sitio específicamente para hexadecimal. Se convierte rápidamente, con la opción de cambiar la codificación, lo usaremos para obtener la bandera
La decodificación del hexadecimal también se puede hacer manualmente con una tabla ASCII [asciitable](http://www.asciitable.com/)


Si aplicamos la conversión nos queda como lo siguiente :
```
picoCTF{p}
```

