# USERNAME -> amcdanymx

# SQL Direct

## Description
Connect to this PostgreSQL server and find the flag!

This challenge launches an instance on demand.  
Its current status is: `NOT_RUNNING`

Launch Instance

## Pistas

- (None)
- 
## Solución

Damos click al boton de lanzar la instancia, en cuanto presionamos nos cambia la instrucción y nos muestra comando de como conectarnos a la DB


```
**

ql -h saturn.picoctf.net -p 50103 -U postgres pico

Contraseña para usuario postgres:

psql (14.4 (Debian 14.4-1+b1), servidor 14.2 (Debian 14.2-1.pgdg110+1))

Digite «help» para obtener ayuda.

  

pico=# help

Está usando psql, la interfaz de línea de órdenes de PostgreSQL.

Digite:  \copyright para ver los términos de distribución

    \h para ayuda de órdenes SQL

    \? para ayuda de órdenes psql

    \g o punto y coma («;») para ejecutar la consulta

    \q para salir

pico=# \h

pico=#

pico=# \l

                            Listado de base de datos

  Nombre   |  Dueño   | Codificación |  Collate   |   Ctype |  Privilegios  

-----------+----------+--------------+------------+------------+-----------------------

 pico  | postgres | UTF8     | en_US.utf8 | en_US.utf8 |

 postgres  | postgres | UTF8     | en_US.utf8 | en_US.utf8 |

 template0 | postgres | UTF8     | en_US.utf8 | en_US.utf8 | =c/postgres      +

        |      |          |        |        | postgres=CTc/postgres

 template1 | postgres | UTF8     | en_US.utf8 | en_US.utf8 | =c/postgres      +

        |      |          |        |        | postgres=CTc/postgres

(4 filas)

  

pico=# \pico

orden \pico no válida

Digite \? para obtener ayuda.

pico=# \c pico

psql (14.4 (Debian 14.4-1+b1), servidor 14.2 (Debian 14.2-1.pgdg110+1))

Ahora está conectado a la base de datos «pico» con el usuario «postgres».

pico=# \dt

     Listado de relaciones

 Esquema | Nombre | Tipo  |  Dueño   

---------+--------+-------+----------

 public  | flags  | tabla | postgres

(1 fila)

  

pico=# SELECT flags

pico-# SELECT flags FROM pico;

ERROR:  syntax error at or near "flags"

LÍNEA 2: SELECT flags FROM pico;

             ^

pico=# SELECT * from flags;

 id | firstname | lastname  |            address             

----+-----------+-----------+----------------------------------------

  1 | Luke  | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}

  2 | Leia  | Organa | Alderaan

  3 | Han   | Solo  | Corellia

(3 filas)

  

pico=#

  
**

```

Para cada iunstruccion en consola con postgres hay la opción de ayuda con help, ahí te dan comandos de como ir moviendote a través de POSTGRES

Al final solo metimos dos sentencias de SQL para mostrar el contenido de la tabla de banderas:

La bandera aparece en el primer registro;
