## Objetivo
How about we take you on an adventure on exploring certificate signing requestsTake a look at this CSR file [here](https://artifacts.picoctf.net/c/426/readmycert.csr).

## Pistas
1. Download the certificate signing request and try to read it.

## Solución
```
┌──(kali㉿kali)-[~/Documents/retosPico/retosCrypto3/readMyCert]
└─$ cat readmycert.csr   
-----BEGIN CERTIFICATE REQUEST-----
MIICpzCCAY8CAQAwPDEmMCQGA1UEAwwdcGljb0NURntyZWFkX215Y2VydF80MWQx
Yzc0Y30xEjAQBgNVBCkMCWN0ZlBsYXllcjCCASIwDQYJKoZIhvcNAQEBBQADggEP
ADCCAQoCggEBAOdcDj2/m1LxBrXb3ch9+2BtKd3b8NFn4USXA5JORPfeGcDdIX4V
SiRkFrbxLOit6SZwoAyWQ7SmWJTtzADbr82qTbVktGJj9YebwK57jpMEL6BPT9YA
cE9AGFtVJycL+IXqtlTqAGq4DjcPtAs5THgIPDJ+aTgRDHP8YItfEFs+aywLd8kS
WSmttEjS874Tc++b9PbQ246IIrtQ701/I1NB0S/inzQvPCui+hLSHgMFkGS4leN7
7xJORGAQueRejKuYnOs6HbAlbK0oIWKR83BxkntDBee8KhOPDynHDgYoblERl8rL
JAfcVogKNSniIztMkzh408V9mbLHOfsr6eUCAwEAAaAmMCQGCSqGSIb3DQEJDjEX
MBUwEwYDVR0lBAwwCgYIKwYBBQUHAwIwDQYJKoZIhvcNAQELBQADggEBAFEyhXpa
nZz/ofFW/31ryCF3nyvNg9pOyIniu8kcpiteSaOkNm4YREBCRwj92X3Wy1MUi/7Z
urXwR1TcRTxLdPqeVBn4nsJclAgZqMKcT0ftz5fAM/Xg5whwBHEBb1qFVN+HGhPo
1TKfhXunICyrjNWvM+2fudM2RPsGb0sBsjLAe1/6OJK82LJBoHQ0GlCPDN1tncrl
lpzHACCFPv7LMVF9BSkZDCQNglU1NYDDelXZezfXLbio/a1RC2k4rs+jorVmFese
elZFzORDsCzlgD87NvBUMZWI8J5+9fZeaWAQQfhwEiZOVn8IcjLUxUraxt4rbI/h
0EUJJuCjGyTjRpQ=
-----END CERTIFICATE REQUEST-----
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/retosPico/retosCrypto3/readMyCert]
└─$ touch certificado.txt
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/retosPico/retosCrypto3/readMyCert]
└─$ open certificado.txt 
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/retosPico/retosCrypto3/readMyCert]
└─$ cat certificado.txt | base64 -d
0��0��0<1&0$U
             picoCTF{read_mycert_41d1c74c}10U)
�0�     *�H��                                   ctfPlayer0�"0
��\=��R�����}�`m)����g�D��ND����!~J$d��,���&p�
                                              �C��X���ۯM�d�bc�����{��/�OO�pO@▒[U''
                                                                                  ����T�j�7�
                                                                                            9L<2~i8
                                                                                                   s�`�_[>k,
                                                                                                            w�Y)��H���s�����ێ�"�P�M#SA�/��4/<+����d���{�ND`��^�����:�%l�(!b��pq�{C��*�)�(nQ���$�V�
5)�#;L�8100U%��9�+���&0$        *�H��
             0
+0      *�H��
�Q2�zZ�����V�}k�!w�+�Nȉ����+^I��6n▒D@B��}��S��ٺ��GT�E<Kt��T���\�OG�ϗ�3��pqoZ�T߇▒��2��{� ,��կ3ퟹ�6D�oK�2�{_�8��زA�t4▒P�
  �m��喜� �>��1Q})
�U55��zU�{7�-����Q$
                  i8�ϣ��f�zVE��C�,��?;6�T1����~��^i`A�p&Nr2��J���+l���E &���F�                                                                                                                   
┌──(kali㉿kali)-[~/Documents/retosPico/retosCrypto3/readMyCert]
└─$ 


```

## Notas adicionales

## Referencias
https://medium.com/@cybermma0/ctf-writeup-picoctf-2023-99ea5d0e28bc



