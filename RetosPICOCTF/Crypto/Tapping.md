# USERNAME -> amcdanymx

#### Description

Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 9422`.


#### PISTAS
- What kind of encoding uses dashes and dots?
- The flag is in the format PICOCTF{}

#### SOLUCIÓN

Usamos nc para revisar la conexión y ver que nos dan, vemos que es un texto en forma de codigo morse, utilizamos una herramienta para codificar en este caso usamos https://gchq.github.io/CyberChef/ y pegamos el codigo que nos dieron


```
picoCTF/tapping [ nc jupiter.challenges.picoctf.org 

.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ..--- -.... ---.. ...-- ---.. ..--- ....- -.... .---- ----- }


```

Si decodificamos nos queda o siguiente
```
PICOCTFM0RS3C0D31SFUN2683824610

```
Acomodando la bandera conociendo ya su estructura:

```
PICOCTF{M0RS3C0D31SFUN2683824610}
```
