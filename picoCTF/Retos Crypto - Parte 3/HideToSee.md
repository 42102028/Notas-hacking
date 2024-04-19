## Objetivo
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/241/atbash.jpg).

## Pistas
1. Download the image and try to extract it.

## Solución
picoCTF{atbash_crack_7142fde9}
```
┌──(kali㉿kali)-[~/Documents/retosPico/retosCrypto3/hideToSee]
└─$ wget https://artifacts.picoctf.net/c/241/atbash.jpg 
--2024-04-18 21:56:40--  https://artifacts.picoctf.net/c/241/atbash.jpg
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.26, 3.161.55.100, 3.161.55.61, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 51510 (50K) [application/octet-stream]
Saving to: ‘atbash.jpg’

atbash.jpg                   100%[=============================================>]  50.30K  --.-KB/s    in 0.02s   

2024-04-18 21:56:40 (1.99 MB/s) - ‘atbash.jpg’ saved [51510/51510]

                                                                                                                   
┌──(kali㉿kali)-[~/Documents/retosPico/retosCrypto3/hideToSee]
└─$ ls
atbash.jpg
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/retosPico/retosCrypto3/hideToSee]
└─$ steghide info atbash.jpg 
Command 'steghide' not found, but can be installed with:
sudo apt install steghide
Do you want to install it? (N/y)y
sudo apt install steghide
[sudo] password for kali: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  libmcrypt4 libmhash2
Suggested packages:
  libmcrypt-dev mcrypt
The following NEW packages will be installed:
  libmcrypt4 libmhash2 steghide
0 upgraded, 3 newly installed, 0 to remove and 524 not upgraded.
Need to get 309 kB of archives.
After this operation, 905 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://kali.darklab.sh/kali kali-rolling/main amd64 libmcrypt4 amd64 2.5.8-7 [72.6 kB]
Get:3 http://kali.darklab.sh/kali kali-rolling/main amd64 steghide amd64 0.5.1-15 [144 kB]
Get:2 http://http.kali.org/kali kali-rolling/main amd64 libmhash2 amd64 0.9.9.9-9+b1 [92.4 kB]
Fetched 309 kB in 1s (328 kB/s)                                     
Selecting previously unselected package libmcrypt4.
(Reading database ... 404140 files and directories currently installed.)
Preparing to unpack .../libmcrypt4_2.5.8-7_amd64.deb ...
Unpacking libmcrypt4 (2.5.8-7) ...
Selecting previously unselected package libmhash2:amd64.
Preparing to unpack .../libmhash2_0.9.9.9-9+b1_amd64.deb ...
Unpacking libmhash2:amd64 (0.9.9.9-9+b1) ...
Selecting previously unselected package steghide.
Preparing to unpack .../steghide_0.5.1-15_amd64.deb ...
Unpacking steghide (0.5.1-15) ...
Setting up libmhash2:amd64 (0.9.9.9-9+b1) ...
Setting up libmcrypt4 (2.5.8-7) ...
Setting up steghide (0.5.1-15) ...
Processing triggers for libc-bin (2.37-12) ...
Processing triggers for man-db (2.12.0-3) ...
Processing triggers for kali-menu (2023.4.7) ...
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/retosPico/retosCrypto3/hideToSee]
└─$ steghide info atbash.jpg
"atbash.jpg":
  format: jpeg
  capacity: 2.4 KB
Try to get information about embedded data ? (y/n) y
Enter passphrase: 
  embedded file "encrypted.txt":
    size: 31.0 Byte
    encrypted: rijndael-128, cbc
    compressed: yes
                                                                                                                                                                               
┌──(kali㉿kali)-[~/Documents/retosPico/retosCrypto3/hideToSee]
└─$ steghide extract -sf atbash.jpg 
Enter passphrase: 
wrote extracted data to "encrypted.txt".
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/retosPico/retosCrypto3/hideToSee]
└─$ ls                             
atbash.jpg encrypted.txt
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/retosPico/retosCrypto3/hideToSee]
└─$ cat encrypted.txt        
krxlXGU{zgyzhs_xizxp_7142uwv9}

```

## Notas adicionales

## Referencias
https://www.dcode.fr/atbash-cipher
https://medium.com/@tommysultanis/picoctf-hidetosee-4d44a3acdf5c



