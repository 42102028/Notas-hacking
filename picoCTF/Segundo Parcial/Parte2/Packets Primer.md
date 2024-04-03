## Objetivo
Download the packet capture file and use packet analysis software to find the flag.

- [Download packet capture](https://artifacts.picoctf.net/c/195/network-dump.flag.pcap)

## Pistas
1. Wireshark, if you can install and use it, is probably the most beginner friendly packet analysis software product.

## Solución

Este comando extrae y muestra una flag de picoCTF de un archivo de captura de red, eliminando los espacios y buscando el patrón específico `picoCTF{...}`
```
┌──(kali㉿kali)-[~/…/retosForensic/segundoParcial/parte2/packetsPrimer]
└─$ wget https://artifacts.picoctf.net/c/195/network-dump.flag.pcap
--2024-04-03 00:24:41--  https://artifacts.picoctf.net/c/195/network-dump.flag.pcap
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.26, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 778 [application/octet-stream]
Saving to: ‘network-dump.flag.pcap’

network-dump.flag.pcap       100%[=============================================>]     778  --.-KB/s    in 0s      

2024-04-03 00:24:41 (35.2 MB/s) - ‘network-dump.flag.pcap’ saved [778/778]

                                                                                                                   
┌──(kali㉿kali)-[~/…/retosForensic/segundoParcial/parte2/packetsPrimer]
└─$ strings network-dump.flag.pcap | tr -d ' ' | grep -oE "picoCTF{.*}"
picoCTF{p4ck37_5h4rk_b9d53765}
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosForensic/segundoParcial/parte2/packetsPrimer]
└─$ 

```

## Notas adicionales

## Referencias
https://me-resilient64.gitbook.io/picoctf-2022-forensics/packets-primer



