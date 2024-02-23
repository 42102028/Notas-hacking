# Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

# Datos de acceso al nivel
ssh bandit15@bandit.labs.overthewire.org -p 2220
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

# Solución
```
bandit15@bandit:~$ nc localhost 30001
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 20 17:51:06 2024 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 20 17:51:06 2024 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 20 17:50:06 2024 GMT; NotAfter: Feb 20 17:51:06 2024 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEIivS1jANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjIwMTc1MDA2WhcNMjQwMjIwMTc1MTA2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC4
XC9dgne8ha9I/vXn4uTtObLhI/PPyLyl4jyDQPp61VtsEMcOb95KhXxdtQiDtzSD
3KXQVFLaPlVGKDWSR9nV+GoazSNPmNLH/IMVrUYxXjYikPxo1jjYKyuqfjV5bNm3
Hz6z4eDl7wNbPRaPAMPo0WU23m9M04bKQHLINfN7Abz3a+7ChLeICrWXiXp9mWfj
PY8cK7Vayz0eHU4Lg64q4jUaXQqZ/ta1RqZEwv7ZuTKctcazpK/u2+h4zvQCPyLh
uDjUXZTLlIuhfjyKUJLQsmYHAQprV6sY3ybFN32dW6MSE0/ApT6Th0LzKeaYxk5b
3NIeaYyPeKsjqFSwy+2zAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQBQ
RXG1k+cB357X43fsiyaCQQh4RbWHOcg1jBes5eiC/H8MyC3ec1znXvOUfqJcWNQJ
9UJDMwbkpo+IcwJiOe9n/D3Zeypv1g+ta8KKLsQ+zcbp5RdltKy7GuO/s5WjVofE
/IHz/5g+IMoqqYLlquQ539CZykPMC9TB9uWfJj/i8faCox4gjtkSCri+27tUZuHi
eYR3zxY1ptsJti/pMaItC6Oc2/pSlotQ4fXdciLZYGXqlmSFBt8Y8/v1YkhME5gN
3HmBV/Zg1SghA57zYsbf3npvQwudr04f2iF493pe0VRN6DfiXTxWkJe1VKuyGHEr
Q4L4OdVlgMSeyYyKgFc7
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
    Session-ID: 93C612E479D9A54751EA150BE4F63A0DEEE88F44CE11E9BE9E259C12EFAF365D
    Session-ID-ctx:
    Resumption PSK: 5BECDD2D8DE05C262777F8CAEA21B1E673D6DADA87D88B80D959B54B89123BDA33BF63A8B056D2EF6986699C94ECFBDC
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 81 c9 7a 81 90 61 a2 44-6e 83 ab 39 4b a2 9f d6   ..z..a.Dn..9K...
    0010 - 0e 7d da 2a 76 f6 3d 0d-19 79 ac 84 c0 a7 bb 0c   .}.*v.=..y......
    0020 - 60 ab 8c 35 84 8f be f6-6c 0d 52 78 dc 55 6c 7d   `..5....l.Rx.Ul}
    0030 - 10 9e b6 94 c7 a3 ab ef-98 60 bc ea 41 c8 f2 65   .........`..A..e
    0040 - c4 b9 a3 ad ec 58 cf 2a-e7 59 c1 a0 c0 72 be f1   .....X.*.Y...r..
    0050 - 65 60 43 21 f9 ec eb 5b-73 ce 7a 72 03 f7 bb e4   e`C!...[s.zr....
    0060 - b9 56 12 8a 92 8c 69 e9-f1 d3 84 eb 08 b0 78 5c   .V....i.......x\
    0070 - 16 cb 35 53 3c 12 89 6b-c9 de 29 39 33 4c 96 7b   ..5S<..k..)93L.{
    0080 - 7e 22 95 8e ec 9f 34 9b-10 6e fd 3d c7 20 3a e9   ~"....4..n.=. :.
    0090 - 36 ac a4 29 33 06 88 ec-d3 13 02 98 9a c9 5f 8b   6..)3........._.
    00a0 - 94 ba aa 90 d9 12 4f ea-0a 41 27 18 35 1f b9 9a   ......O..A'.5...
    00b0 - 6f 1d 1b aa a6 4e 7b 10-11 9d 4d 2c 1a e2 ef 27   o....N{...M,...'
    00c0 - 32 6f d4 ec 5c 93 e6 c9-c9 bf 92 a3 b8 a8 c8 4e   2o..\..........N

    Start Time: 1708457245
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
    Session-ID: EC88BAB6EA99CC21D72F3A304BB1B0B90F1CDAD07B6FBA6A3C5CDA80682757CE
    Session-ID-ctx:
    Resumption PSK: 831BD47073F263C85FC648ACAAD5F8259D5DED0634A3EA73A9FE7C7F1931210A0C4F0ABD0A3538D777AD740C1CDACE25
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 81 c9 7a 81 90 61 a2 44-6e 83 ab 39 4b a2 9f d6   ..z..a.Dn..9K...
    0010 - fc e8 a7 77 63 26 34 31-6b 1e 3c 09 5c 09 e8 13   ...wc&41k.<.\...
    0020 - 46 f6 07 e7 05 cc c7 6d-53 3c 67 5a b4 a1 b3 21   F......mS<gZ...!
    0030 - 17 be e5 6f 02 92 a6 52-c3 74 d3 4f 9f 7b bd 30   ...o...R.t.O.{.0
    0040 - 43 5b 6a 79 bf 3b 93 5b-70 ba 85 20 84 cb 86 ad   C[jy.;.[p.. ....
    0050 - 46 fb f8 16 bb c2 e0 59-b0 06 de a2 0b 75 1c de   F......Y.....u..
    0060 - 96 f2 e6 4a fc 69 15 90-f1 a7 b2 9b f6 6f f0 53   ...J.i.......o.S
    0070 - 08 a4 fc a1 62 61 6e b5-2e 11 5b f0 c3 4f 87 5d   ....ban...[..O.]
    0080 - 63 d9 29 75 60 ad 3e 32-12 99 03 be 71 96 ca e9   c.)u`.>2....q...
    0090 - b4 f0 7a ca dc bd 35 30-2f 93 71 5a 7b b2 6f f9   ..z...50/.qZ{.o.
    00a0 - 7e bb 1d 3c bc 82 ce d4-60 fd 85 1f ac 44 2c 8d   ~..<....`....D,.
    00b0 - a1 2f 69 67 0f 2f f6 77-63 2c dd 23 42 71 3f 84   ./ig./.wc,.#Bq?.
    00c0 - f0 e5 66 75 64 d3 d8 9e-59 3b 5c d1 a7 73 ee b1   ..fud...Y;\..s..

    Start Time: 1708457245
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

# Notas adicionales


# Referencias