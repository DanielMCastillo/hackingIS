## Descripción

When a communication protocol is used that does not encrypt the information, it travels in plain text, putting the information at risk. Can you find the flag of this enchilada?

## Solución
```
Hay que buscar en el flujo TCP de wireshark algo de importancia, en este caso un texto encriptado en base64, se decodifica y se obtiene la bandera ZmxhZ01Ye0VuY2gxbGFkYVIwamF5VmVyZDN9Cg==

flagMX{Ench1ladaR0jayVerd3}
```