
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
![[Pasted image 20220922182744.png]]
## 2/3
En el archivo de estilos CSS podremos encontrar la segunda parte de la bandera 2/3
![[Pasted image 20220922182912.png]]

## 3/3

Finalmente en el archivo JS podremos encontrar la tercera parte de la bandea 3/3
![[Pasted image 20220922183033.png]]

Finalmente armamos la bandera con cada parte y la entregamos:
![[Pasted image 20220922183100.png]]