# USERNAME -> amcdanymx

#### Description

Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/264/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?


#### PISTAS
- How can you be sure of the redaction?

#### SOLUCIÓN
Descargamos el archivo, vemos que tiene una extención PDF, lo abrimos, en el archivo aparecen campos en color negro en forma de censura, lo unico que hacemos es copiar el texto normal y lo pegamos en otro lado, encontramos la bandera:


```
**  

Financial Report for ABC Labs, Kigali, Rwanda for the year 2021.

Breakdown - Just painted over in MS word.

Cost Benefit Analysis

Credit Debit

This is not the flag, keep looking

Expenses from the

picoCTF{C4n_Y0u_S33_m3_fully}

Redacted document.

**

```

```
picoCTF{C4n_Y0u_S33_m3_fully}

```
