# USERNAME -> amcdanymx


#### Description

A type of transposition cipher is the rail fence cipher, which is described [here](https://en.wikipedia.org/wiki/Rail_fence_cipher). Here is one such cipher encrypted using the rail fence with 4 rails. Can you decrypt it?Download the message [here](https://artifacts.picoctf.net/c/274/message.txt).Put the decoded message in the picoCTF flag format, `picoCTF{decoded_message}`.


#### PISTAS
- Once you've understood how the cipher works, it's best to draw it out yourself on paper


#### SOLUCIÓN
En este reto nos dan un archivo de texto con un texto encriptado, utiliza lo que se llama rail fence, utilizaremos una herramienta para desencriptar:
**https://www.boxentriq.com/code-breaking/rail-fence-cipher**

```
ponemos la bandera encirptada en la herramienta y nos da la desencriptación y la bandera

Encriptada:
Ta _7N6DDDhlg:W3D_H3C31N__0D3ef sHR053F38N43D0F i33___NA

Desencriptada:
The flag is: WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_D00AFDD3
```

