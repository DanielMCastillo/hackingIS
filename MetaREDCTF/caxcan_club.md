## Descripción

by hackadvisermx

I want to join to the Caxcan club, but they have the **weirdest passwords**! I've managed to intercept the program they use to authenticate the passwords, but I don't know how to figure it out. Can you figure out the password for me.

The Caxcan were a partly nomadic indigenous people of Mexico. Under their leader, Tenamaztle, the Caxcan were allied with the Zacatecos against the Spaniards during the Mixtón Rebellion in 1540-42.

## Solución

Se duplica el método swoop cambiando la forma de orden negativa sin hacer join, despues se hace un forech a la lista obtenida del swoop agregando cada elemento al string password, al terminar el foreach se cambia el orden de password al inverso con un [::-1] se manda a imprimir y esa es la bandera.

```
def swoopPass():
     noOrderPassword = "}zudidsbybwxaqaqehxbebimt`jks{XNidpk"
     text = list(noOrderPassword)
     for i in range(len(text)):
             if text[i] not in '{}':
                     text[i] = chr(ord(text[i]) - (i % 6))
     return text

password = ''

for elem in swoopPass():
    password+=elem
    
password = password[::-1]

print(password)

def roll(text):
    return text[::-1]

def swoop(text):
    text = list(text)
    for i in range(len(text)):
        if text[i] not in '{}':
            text[i] = chr(ord(text[i]) + (i % 6))
    return ''.join(text)

if swoop(roll(password)) == "}zudidsbybwxaqaqehxbebimt`jks{XNidpk":
	print("Welcome in!")
else:
    print("Sorry, wrong password.")
```