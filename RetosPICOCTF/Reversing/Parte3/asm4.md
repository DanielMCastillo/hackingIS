# USERNAME -> amcdanymx

#### Description

What will asm4("picoCTF_a3112") return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/80186ad81f4a1569b480e7fbf68b29ca/test.S)


#### PISTAS
- Treat the Array argument as a pointer

#### SOLUCIÓN

Nos dan un archivo en lenguaje ensamblador el cual modificaremos para poder compilarlo, nos queda así:
```

.intel_syntax noprefix

.global asm4

  

asm4:

     push   ebp

     mov ebp,esp

     push   ebx

     sub esp,0x10

     mov DWORD PTR [ebp-0x10],0x246

     mov DWORD PTR [ebp-0xc],0x0

     jmp asm4+27

     add DWORD PTR [ebp-0xc],0x1

     mov edx,DWORD PTR [ebp-0xc]

     mov eax,DWORD PTR [ebp+0x8]

     add eax,edx

     movzx  eax,BYTE PTR [eax]

     test   al,al

     jne asm4+23

     mov DWORD PTR [ebp-0x8],0x1

     jmp asm4+138

     mov edx,DWORD PTR [ebp-0x8]

     mov eax,DWORD PTR [ebp+0x8]

     add eax,edx

     movzx  eax,BYTE PTR [eax]

     movsx  edx,al

     mov eax,DWORD PTR [ebp-0x8]

     lea ecx,[eax-0x1]

     mov eax,DWORD PTR [ebp+0x8]

     add eax,ecx

     movzx  eax,BYTE PTR [eax]

     movsx  eax,al

     sub edx,eax

     mov eax,edx

     mov edx,eax

     mov eax,DWORD PTR [ebp-0x10]

     lea ebx,[edx+eax*1]

     mov eax,DWORD PTR [ebp-0x8]

     lea edx,[eax+0x1]

     mov eax,DWORD PTR [ebp+0x8]

     add eax,edx

     movzx  eax,BYTE PTR [eax]

     movsx  edx,al

     mov ecx,DWORD PTR [ebp-0x8]

     mov eax,DWORD PTR [ebp+0x8]

     add eax,ecx

     movzx  eax,BYTE PTR [eax]

     movsx  eax,al

     sub edx,eax

     mov eax,edx

     add eax,ebx

     mov DWORD PTR [ebp-0x10],eax

     add DWORD PTR [ebp-0x8],0x1

     mov eax,DWORD PTR [ebp-0xc]

     sub eax,0x1

     cmp DWORD PTR [ebp-0x8],eax

     jl asm4+51

     mov eax,DWORD PTR [ebp-0x10]

     add esp,0x10

     pop ebx

     pop ebp

     ret

```

Al igual crearemos un archivo en c el cual se ejecutara a la par del otro archivo:

```
#include <stdio.h>

int main(){

     printf("Flag: 0x%x\n", asm4("picoCTF_a3112"));
}




```

Compilamos ambos programas y los juntamos:
```
**gcc -m32 -c solve.c -o solve.o -w

gcc -m32 -c chal.s -o chal.o        

gcc -m32 a.out solve.o chal.o**

```

Para el asm4 de asm4("picoCTF_a3112") nos regresa:
```
0x1D0

```
Y esa es la bandera. 