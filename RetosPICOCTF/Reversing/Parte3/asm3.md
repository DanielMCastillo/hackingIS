# USERNAME -> amcdanymx


#### Description

What does asm3(0xd73346ed,0xd48672ae,0xd3c8b139) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/17c5620fcffa388fe518d31cb4dd99a0/test.S)

#### PISTAS
- more(?) [registers](https://wiki.skullsecurity.org/index.php?title=Registers)

#### SOLUCIÓN

Seguimos con la teoría de ensamblador, en este caso haremos uso de una herramienta para saber como se guardan los registros que es lo que nos pide el reto, la herramienta es:
https://carlosrafaelgn.com.br/Asm86/

Código acomodado para usarlo en la herramienta y simular:

Pasamos en la función de inicio los 3 valores quie nos dan por medio del push, de manera inversa como se comporta la pila

```
start:
    push 0xd3c8b139
    push 0xd48672ae
    push 0xd73346ed
    call asm3

asm3:
    push   ebp
	mov ebp,esp
	xor eax,eax
	mov ah,BYTE PTR [ebp+0xa]
	shl ax,0x10
	sub al,BYTE PTR [ebp+0xc]
	add ah,BYTE PTR [ebp+0xd]
	xor ax,WORD PTR [ebp+0x10]
	nop
	pop ebp

ret
```

Salida de registros al ejectuar:

```
Flags
Carry  
0
  
Dir  
0
Int  
0
  
Overflow  
0
Sign  
1
  
Zero  

EAX  
**0x0000C36B**
  
EBX  
0x00000000
ECX  
0x00000000
  
EDX  
0x00000000
ESI  
0x00000000
  
EDI  
0x00000000
EBP  
0x000203EC
  
ESP  
0x000203EC
EIP  
0x00020430
Ln 16, Col 5



```

La bandera es el campo EAX:
```
0x0000C36B

```