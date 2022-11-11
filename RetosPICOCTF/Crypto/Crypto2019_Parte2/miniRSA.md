# USERNAME -> amcdanymx


#### Description

Let's decrypt this: [ciphertext](https://jupiter.challenges.picoctf.org/static/ee7e2388b45f521b285334abb5a63771/ciphertext)? Something seems a bit small.


#### Pistas
- RSA [tutorial](https://en.wikipedia.org/wiki/RSA_(cryptosystem))
- How could having too small an e affect the security of this 2048 bit key?
- Make sure you don't lose precision, the numbers are pretty big (besides the e value)
- 
#### SOLUCIÓN

Descargamos el archivo que nos dan, para este desafío necesitaremos ciertas librerías que manejan texto plano de muchos caracteres y que especificamente nos ayudarán en el desafío, como anteriormente vimos en la teoría de RSA la variable c es texto cifrado, e elexponente de la llave publica, n es el modulo de multiplicado de p por q
Debemos saber como un exponente pequeño puede afectar a una llave, al ser numeros muy grandes debemos de tener una gran precisión
Usaremos las misma formulas

```
amcdanymx at kali in ~/picoCTF/miniRSA

○ cat ciphertext
N: 29331922499794985782735976045591164936683059380558950386560160105740343201513369939006307531165922708949619162698623675349030430859547825708994708321803705309459438099340427770580064400911431856656901982789948285309956111848686906152664473350940486507451771223435835260168971210087470894448460745593956840586530527915802541450092946574694809584880896601317519794442862977471129319781313161842056501715040555964011899589002863730868679527184420789010551475067862907739054966183120621407246398518098981106431219207697870293412176440482900183550467375190239898455201170831410460483829448603477361305838743852756938687673

e: 3

  

ciphertext (c): 2205316413931134031074603746928247799030155221252519872649649212867614751848436763801274360463406171277838056821437115883619169702963504606017565783537203207707757768473109845162808575425972525116337319108047893250549462147185741761825125

  

amcdanymx at kali in ~/picoCTF/miniRSA

○ python3 -m pip install gmpy2

Defaulting to user installation because normal site-packages is not writeable

Collecting gmpy2

  Downloading gmpy2-2.1.2-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (3.6 MB)

  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 3.6/3.6 MB 616.9 kB/s eta 0:00:00

Installing collected packages: gmpy2

Successfully installed gmpy2-2.1.2
```

En python calculamos con las librerias de lo que instalamos
```

─amcdanymx@kali in ~

╰$ python3

Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux

Type "help", "copyright", "credits" or "license" for more information.

>>> from gmpy2 import *

>>> from Crypto.Util.number import long_to_bytes

>>> gmpy2 .get_context().precision=2048

>>> e = 3

>>> c = 2205316413931134031074603746928247799030155221252519872649649212867614751848436763801274360463406171277838056821437115883619169702963504606017565783537203207707757768473109845162808575425972525116337319108047893250549462147185741761825125

>>> root, exact = iroot(c,e)

>>> root

mpz(13016382529449106065894479374027604750406953699090365388202874238148389207291005)

>>> print(long_to_bytes(root))

b'picoCTF{n33d_a_lArg3r_e_606ce004}'


```

Tenemos la bandera:

```


picoCTF{n33d_a_lArg3r_e_606ce004}


```
