# USERNAME -> amcdanymx

#### Description

What does asm1(0x2e0) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/f1c2358ff7d1e9386e41552c549cf2f6/test.S)

#### PISTAS
- assembly [conditions](https://www.tutorialspoint.com/assembly_programming/assembly_conditions.htm)

#### SOLUCIÓN

Viendo las reglas, conidciones en el lenguaje ensamblador podemos ver como comparar dichas instrucciones que vienen en el reto, a lo que corresponde cm, mov, add, sub etc, y como acomodar y comparar con los valores, así como ir moviendonos a las siguientes instrucciones:

```
  **GNU nano 6.3                                       test.S *                                              
[ 0x2e0] eax


asm1:

     <+0>:   push   ebp

     <+1>:   mov ebp,esp

  

     <+3>:   cmp DWORD PTR [ebp+0x8],0x3fb

     <+10>:  jg 0x512 <asm1+37>

     <+12>:  cmp DWORD PTR [ebp+0x8],0x280

     <+19>:  jne 0x50a <asm1+29>

     <+21>:  mov eax,DWORD PTR [ebp+0x8]

     <+24>:  add eax,0xa

     <+27>:  jmp 0x529 <asm1+60>

     <+29>:  mov eax,DWORD PTR [ebp+0x8]

     <+32>:  sub eax,0xa

     <+35>:  jmp 0x529 <asm1+60>

     <+37>:  cmp DWORD PTR [ebp+0x8],0x559

     <+44>:  jne 0x523 <asm1+54>

     <+46>:  mov eax,DWORD PTR [ebp+0x8]

     <+49>:  sub eax,0xa

     <+52>:  jmp 0x529 <asm1+60>

     <+54>:  mov eax,DWORD PTR [ebp+0x8]

     <+57>:  add eax,0xa


     <+60>:  pop ebp

     <+61>:  ret**
```
Operaciones en python3:

```
amcdanymx@kali:~|⇒  python3

Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux

Type "help", "copyright", "credits" or "license" for more information.

>>> 0x2e0 > 0x3fb

False

>>> 0x2e0 != 0x280

True

>>> 0x2e0 - 0xa

726

>>> hex(0x2e0-0xa)

'0x2d6'

```

La bandera no está en el formato habitual, entonces queda como: 

```
'0x2d6'
```
