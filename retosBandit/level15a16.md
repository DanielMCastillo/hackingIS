# BANDIT LEVEL 15 -> LEVEL 16

## Objetivo

-   find the password that can be obtained by submitting the password of the current level to port 30001 on localhost using SSL encryption.

## Datos de acceso

-   Host: bandit.labs.overthewire.org
-   Port: 2220
-   User: bandit15
-   Password: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Solución

-   With openSSL you can make a command that helps you connect to port 30001, then put the actual password and you will get the next one. "openssl s_client -connect localhost:30001 -ign_eof", then put the current password.

```
bandit15@bandit:~$ bandit15@bandit:~$ openssl s_client -connect localhost:30001 -ign_eof
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep  1 06:31:12 2022 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep  1 06:31:12 2022 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep  1 06:30:12 2022 GMT; NotAfter: Sep  1 06:31:12 2022 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEHn8h8jANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjIwOTAxMDYzMDEyWhcNMjIwOTAxMDYzMTEyWjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDK
u/UD6yArwj259J4o2IVQQGvM/oGVIiYYppFd1jxltmQ03SOUVg+4px+7qOJuCbxA
AH9NCAl55r7v/VDlwGkpu4c2GaqR3zSAlidrtJjrVFZP/QilXdv0uV35N4i30BuT
DdI+FzlYcQx7ztZdtDxp61FTjET4BIcFmSzMQLitpYeeiVcKLXTPnsF8216drWjQ
0Ucb+3RvGgPo/rKPra8/7WYFa8ALdnu2rwP07ndtMDL3iJF9VMuBsr8UuTdsktwa
174QGx0f3RFkcKJ1foxYnSoHvy0BhxVGguMKuinY6cyLELwnjcAp4A2oGI438GnV
whe39ZlCkGved612QLhDAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQDE
2X2mgxYDvujnIAL2Qbs8JnUBFe3lZsRZJbPgko3MZ4lScB5Rbz+vb6q6s0KGGMjh
sKweg4BtG4sQWDIwX2yd4XwJa8rrGWuoA4kgCQ/jJhFZrbCPbDN3sbzX8Tql+epd
oJyQcvLOkWDazRPgx0i4dMXIgUv0kbE+NCvj2waXHldMyjT6GFL2bdv/Xd8ffnXg
wlggJKKIzl0RMp/5z5n1bPMoLVl5HcUG3UzOsTcqcSThTr3JXeWLjaL0qJfAfcw5
V+GM2tGTQB3c4jvISAl5RAARpvFUMc4d4hKd6aesRcFHZfbtSjxglPFmeL1VGxJ9
EIg5c/xwHOE6dgDA2WdS
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: CBF1100ED0FDA55798D190FB9DED3473C16DCCE273189BB7C86162934F5377A2
    Session-ID-ctx:
    Resumption PSK: 53AEC14AAA7A3B1B6E6CF1DE70AFA82ED4AB602BB3D87D3D1FFCE309A343888CA102CCD171E381C2574EFEA57DC79675
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 09 86 a0 aa 25 48 38 1d-0e b1 8d f8 fa 82 ac 33   ....%H8........3
    0010 - 2a 62 48 c0 5a 30 5c 2c-d2 e9 30 60 44 31 f6 75   *bH.Z0\,..0`D1.u
    0020 - f1 9b ce b1 2c 79 b1 8f-1d 9a 89 d4 cc 73 44 30   ....,y.......sD0
    0030 - 0a 81 5b c8 4f ad 0c 2f-86 ab a9 66 c5 34 8a b9   ..[.O../...f.4..
    0040 - e5 f7 18 0b 02 32 a9 f7-c9 ad 37 e1 23 98 f0 35   .....2....7.#..5
    0050 - 28 30 40 4d 5d 5f db bc-8b 84 6d 71 04 b6 f6 7c   (0@M]_....mq...|
    0060 - 7d 5b be d7 1b b2 0b 8d-84 92 ab a2 60 21 43 29   }[..........`!C)
    0070 - f4 d4 48 78 9b b6 0e 3d-61 da 32 e3 62 bb bb 6a   ..Hx...=a.2.b..j
    0080 - e2 fe eb 74 ac 7e 3e b7-e9 b7 69 5e 21 27 c1 c1   ...t.~>...i^!'..
    0090 - be 9d 1d 6f 6a 23 d2 7c-c6 c6 1b 08 fb 36 cb d6   ...oj#.|.....6..
    00a0 - 0e 9b b8 7b 92 7a 4c df-53 e9 5c c0 14 57 81 86   ...{.zL.S.\..W..
    00b0 - ba 8f 49 ab 04 de c5 c0-ba 1f e7 58 01 e7 ea 41   ..I........X...A
    00c0 - 36 89 b6 94 c4 e6 02 ce-2f b2 09 56 bc 28 c3 5f   6......./..V.(._

    Start Time: 1662303167
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 36F2F746779F2B8678A2FB913253EA13D4F51D0C1A5D72D5287B2DAC4A4B5D9C
    Session-ID-ctx:
    Resumption PSK: 8681A4F156EF9B5294B80DD9D06A2D3FA0C7BAB3324E1FA701D6A1A7DAA52A791077EAF9BC92627B062A308E722CF333
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 09 86 a0 aa 25 48 38 1d-0e b1 8d f8 fa 82 ac 33   ....%H8........3
    0010 - 80 09 07 52 c0 c5 d0 65-f8 b8 9a 6c e6 6f 8b 01   ...R...e...l.o..
    0020 - 66 76 24 ef 80 53 4e bc-9f bc 0f bf cd 87 33 63   fv$..SN.......3c
    0030 - 27 e0 7f d7 47 18 8d 1c-0d 49 18 c7 37 4f 55 fe   '...G....I..7OU.
    0040 - 43 88 c8 c3 6c 49 0b ce-c0 48 8a 69 a1 db 67 1b   C...lI...H.i..g.
    0050 - 73 ce 2f 23 fd 03 33 92-40 59 cb f1 67 0c d9 0c   s./#..3.@Y..g...
    0060 - 7a c4 6b c6 b1 46 5d 57-90 39 c6 d0 8c 6f 61 13   z.k..F]W.9...oa.
    0070 - ab 62 a0 fe c2 e9 d7 43-a1 4a 11 95 38 15 e9 6f   .b.....C.J..8..o
    0080 - a8 81 6a 6e d7 03 18 95-05 e4 67 2f 1c b9 40 00   ..jn......g/..@.
    0090 - 39 2f 9f 20 55 e8 68 51-b7 98 29 d3 38 73 59 ba   9/. U.hQ..).8sY.
    00a0 - ac 9e a2 20 12 0b fe ce-66 ea a2 a3 40 bc ca d6   ... ....f...@...
    00b0 - a5 8e 0b ad c9 c6 a5 f6-96 8b c6 87 2d d5 d2 a0   ............-...
    00c0 - 3e f2 b0 d4 d6 53 f9 57-ab 5d c8 e5 b2 c8 85 27   >....S.W.].....'

    Start Time: 1662303167
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
bandit15@bandit:~$
```

## Notas adicionales

-   Open SSL is a tool that provides encryption techniques for data security.