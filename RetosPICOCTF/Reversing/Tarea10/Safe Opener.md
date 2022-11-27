# USERNAME -> amcdanymx

#### Description

Can you open this safe?I forgot the key to my safe but this [program](https://artifacts.picoctf.net/c/463/SafeOpener.java) is supposed to help me with retrieving the lost key. Can you help me unlock my safe?Put the password you recover into the picoCTF flag format like:`picoCTF{password}`

#### PISTAS
- None

#### SOLUCIÓN

En este desafío nos dan un archivo ccon extensión .java, analizando el código  nos encontramos con un método llamado openSafe, en el se pasa como parametro la password, después compara eso con una variable llamada encodedkey, dicha variable está en base64, solo hay que decodificar a mano eso, en nuestro caso en consola y ver que sucede:
```  
   public static boolean openSafe(String password) {

       String encodedkey = "cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz";

       if (password.equals(encodedkey)) {

           System.out.println("Sesame open");

           return true;

       }

       else {

           System.out.println("Password is incorrect\n");

           return false;

       }

   }

```

```
amcdanymx:safeopener/ $ ls                                       
	SafeOpener.java
    
amcdanymx:safeopener/ $ code SafeOpener.java                            

amcdanymx:safeopener/ $ echo cGwzYXMzX2wzdF9tM18xbnQwX3RoM19zYWYz | base64 -d                          

pl3as3_l3t_m3_1nt0_th3_saf3%

```

Como vemos al usar echo y el parametro en consola de base64 para decodificar obtenemos lo siguiente: pl3as3_l3t_m3_1nt0_th3_saf3

Ya solo lo acomodamos como formato de la flag:

picoCTF{pl3as3_l3t_m3_1nt0_th3_saf3}

