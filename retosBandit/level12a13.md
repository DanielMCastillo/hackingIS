# BANDIT LEVEL 12 -> LEVEL 13

# Objetivo

The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

## Commands you may need to solve this level

grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

## Helpful Reading Material

-   [Rot13 on Wikipedia](https://en.wikipedia.org/wiki/Rot13)



# Datos de acceso

USERNAME: **bandit11**
PASSWORD:  5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu

# Solución
Revisamos el archivo `data.txt`, y encontramos que los datos de este no tienen sentido:

Siguiendo las instrucciones, vemos que las letras originales fueron reemplazadas por una letra 13 posiciones después del alfabeto.

Como ejemplo, pasaremos la palabra hello a ROT13

-   Si a la letra `H` la movemos 13 lugares en el [alfabeto inglés](https://www.inglessencillo.com/el-alfabeto), quedaría con la letra `U`
-   Si hacemos lo mismo con la `E`, sería `R`
-   La `L` sería `Y`
-   Y la `O` sería `B`

Entonces, si pasamos la palabra `hello` a ROT13, quedaría `uryyb`.

Ahora que sabemos como usar ROT13, lo que haremos es usar el comando `tr`, que nos permite traducir o eliminar caracteres. Por lo tanto, usando este método, moveremos la letra `A` 13 posiciones, quedando en la letra `N`, y así con cada carácter.

Al usar `tr`, primero escribimos todos los caracteres a traducir (mayúsculas y minúsculas) `'A-Za-z'`. Luego indicamos los caracteres movidos 13 posiciones `'N-ZA-Nn-za-m'`:

- **cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m**

# Notas adicionales




