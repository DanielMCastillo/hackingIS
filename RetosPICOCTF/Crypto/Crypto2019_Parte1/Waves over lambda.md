#### Description

We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 13758`.

#### Pistas
Flag is not in the usual flag format

#### SOLUCIÓN


Usamos nc para revisar la conexión y ver que nos dan, vemos que es un texto en forma de codigo a lo que se le conoce cifrado por substitución donde se encriptan unas letras o mezclan y tienen una llave, utilizamos una herramienta para codificar en este caso usamos https://www.guballa.de/substitution-solver y pegamos el codigo que nos dieron,


```
picoCTF/wavesoverlambda [ nc jupiter.challenges.picoctf.org 13758                                       ] 2:39

-------------------------------------------------------------------------------

rhcmpjbx zsps nx dhwp oyjm - opsqwscrd_nx_r_hlsp_yjugij_iclbopbjdw

-------------------------------------------------------------------------------

zjlncm zji xhus bnus jb ud inxthxjy ezsc nc yhcihc, n zji lnxnbsi bzs gpnbnxz uwxswu, jci ujis xsjprz juhcm bzs ghhfx jci ujtx nc bzs yngpjpd psmjpincm bpjcxdyljcnj; nb zji xbpwrf us bzjb xhus ohpsfcheysims ho bzs rhwcbpd rhwyi zjpiyd ojny bh zjls xhus nuthpbjcrs nc isjyncm enbz j chgysujc ho bzjb rhwcbpd. n onci bzjb bzs inxbpnrb zs cjusi nx nc bzs svbpsus sjxb ho bzs rhwcbpd, kwxb hc bzs ghpispx ho bzpss xbjbsx, bpjcxdyljcnj, uhyijlnj jci gwfhlncj, nc bzs unixb ho bzs rjptjbznjc uhwcbjncx; hcs ho bzs enyisxb jci ysjxb fchec thpbnhcx ho swphts. n ejx chb jgys bh ynmzb hc jcd ujt hp ehpf mnlncm bzs svjrb yhrjynbd ho bzs rjxbys ipjrwyj, jx bzsps jps ch ujtx ho bznx rhwcbpd jx dsb bh rhutjps enbz hwp hec hpicjcrs xwplsd ujtx; gwb n ohwci bzjb gnxbpnba, bzs thxb bhec cjusi gd rhwcb ipjrwyj, nx j ojnpyd esyy-fchec tyjrs. n xzjyy scbsp zsps xhus ho ud chbsx, jx bzsd ujd psopsxz ud usuhpd ezsc n bjyf hlsp ud bpjlsyx enbz uncj.
```

Después de la decodificación nos da la llave
  
```
congrats here is your flag - frequency_is_c_over_lambda_dnvtfrtayu

-------------------------------------------------------------------------------

having had some time at my disposal when in london, i had visited the british museum, and made search among the books and maps in the library regarding transylvania; it had struck me that some foreknowledge of the country could hardly fail to have some importance in dealing with a nobleman of that country. i find that the district he named is in the extreme east of the country, just on the borders of three states, transylvania, moldavia and bukovina, in the midst of the carpathian mountains; one of the wildest and least known portions of europe. i was not able to light on any map or work giving the exact locality of the castle dracula, as there are no maps of this country as yet to compare with our own ordnance survey maps; but i found that bistritz, the post town named by count dracula, is a fairly well-known place. i shall enter here some of my notes, as they may refresh my memory when i talk over my travels with mina.

  
  
**

```


La bandera sería así ya que no sigue ahora el mismo formato:

```
frequency_is_c_over_lambda_dnvtfrtayu
```