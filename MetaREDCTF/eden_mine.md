## Descripción

I downloaded one of my friend's files that describe how **frequently** he visits the "eden mine" in Zacatecas, México, but i think there might be more to it.

The most important time of the "eden mine" was during the XVII and XVIII centuries when production was mainly based in silver and gold. Given the floods in its shafts and how close it is to the city, in 1960 the exploitation of the mine ended, a little after it was adapted for tourism, being the most visited mine in the country by national and foreign tourists.

## Solución

Hay que analizar la frecuencia de cada letra y convertirlo a char

```
import string

stringIn = open('edenmine.txt', 'r').read()
flag=''
for c in string.ascii_letters:
    char=c
    count=0
    i=0
    while(i<len(stringIn)):
        if(stringIn[i]==char):
            count=count+1
        i=i+1
    flag+=chr(count)
print(flag)
```
flagMX{I_10v3_fr3qu3cies_XD}