## Descripción

by hackadvisermx

Juan the explororer extracted this file from the site on the last expedition, but it appears to have been **corrupted**. This may be the secret code to open Francisco Villa vault that was found inside the "Cerro de la Bufa" in Zacatecas City. Can you identify what it once was and possibly fix it ? .

On June 23, 1914, this place was the scene of the "La toma de Zacatecas" (1914), where the revolutionary troops of General Francisco Villa defeated the Huertista army, defining the destiny of the nation.

## Solución
```
Se tuvo que reparar el encabezado de acuerdo al formato PNG

Original
00000000: 5047 890a 4e0d 0a1a 0d48 4400 5200 0049  PG..N....HD.R..I

Modificado
00000000: 8950 4e47 0d0a 1a0a 0000 000d 4948 4452  .PNG........IHDR
```

flagMX{you_found_my_secret_vault}