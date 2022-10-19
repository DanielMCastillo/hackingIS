## Descripción

**This recipe is very strange, it doesn't seem to match with a delicious Mexican food, discover the secret Mexican food.**

Mexican food.

Ingredients. 81 ml beer 103 cups oil 77 g salt 83 g sugar 88 ml water 123 g chili 99 g cream 82 totopos 101 g guacamole 108 tomatoes 105 g fish 78 g cilantro 102 g chicken 72 ml milk 117 g cinnamon 97 g lard 125 g pepper 95 g honey

Method. Put pepper into the mixing bowl. Put sugar into the mixing bowl. Put guacamole into the mixing bowl. Put tomatoes into the mixing bowl. Put fish into the mixing bowl. Put cinnamon into the mixing bowl. Put beer into the mixing bowl. Put lard into the mixing bowl. Put tomatoes into the mixing bowl. Put fish into the mixing bowl. Put milk into the mixing bowl. Put cream into the mixing bowl. Put honey into the mixing bowl. Put cilantro into the mixing bowl. Put guacamole into the mixing bowl. Put guacamole into the mixing bowl. Put totopos into the mixing bowl. Put oil into the mixing bowl. Put chili into the mixing bowl. Put water into the mixing bowl. Put salt into the mixing bowl. Put oil into the mixing bowl. Put lard into the mixing bowl. Put tomatoes into the mixing bowl. Put chicken into the mixing bowl. Liquefy contents of the mixing bowl. Pour contents of the mixing bowl into the baking dish.

## Solución

Se tiene que seguir la receta que describe, cada ingrediente es un número para convertir a char, el resultado de la bandera se tiene que hacer un reverse, porque la receta está dictada al revés

```
vals = [125,83,101,108,105,117,81,97,108,105,72,99,95,78,101,101,82,103,123,88,77,103,97,108,102]

flag=''
for c in vals:
    flag+=chr(c)
print(flag[::-1])

flagMX{gReeN_cHilaQuileS}
```