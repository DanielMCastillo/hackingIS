# USERNAME -> amcdanymx


#### Description

This vault uses ASCII encoding for the password. The source code for this vault is here: [VaultDoor4.java](https://jupiter.challenges.picoctf.org/static/c695ee23309d453a3ef369c34cc1bccb/VaultDoor4.java)

#### PISTAS 
- Use a search engine to find an "ASCII table".
- You will also need to know the difference between octal, decimal, and hexadecimal numbers.

#### SOLUCIÓN
Utilizamos la herramienta de desarrolladorde firefox, en este caso la terminal para crear codigo javascript y decifrar el código que nos dan con la password.
En este caso el código de java que nos dan tenemos caracteres ASCII, hexadecimal y octales, tenemos que tratar de resoverlo según sus respectivos caracteres

Javascript code
```
**

String.fromCharCode(106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,

         0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,

         0142, 0131, 0164, 063 , 0163, 0137, 070 , 0146)

"jU5t_4_bUnCh_0f_bYt3s_8f"

String.fromCharCode(106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,

         0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,

         0142, 0131, 0164, 063 , 0163, 0137, 070 , 0146,)

"jU5t_4_bUnCh_0f_bYt3s_8f"

salida = String.fromCharCode(106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,

         0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,

         0142, 0131, 0164, 063 , 0163, 0137, 070 , 0146) + ['4' , 'a' , '6' , 'c' , 'b' , 'f' , '3' , 'b'].join("")

"jU5t_4_bUnCh_0f_bYt3s_8f4a6cbf3b"

console.log(salida)

jU5t_4_bUnCh_0f_bYt3s_8f4a6cbf3b


```

Bandera acomodada:
```
picoCTF{jU5t_4_bUnCh_0f_bYt3s_8f4a6cbf3b}

```