## Objetivo
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm) has extraordinarily helpful information...
## Pistas

## Solución
```
arcf99-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm
--2024-02-27 18:37:38--  https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm.3'

warm.3                                                   100%[==================================================================================================================================>]  10.68K  --.-KB/s    in 0s      

2024-02-27 18:37:38 (148 MB/s) - 'warm.3' saved [10936/10936]

arcf99-picoctf@webshell:~$ chmod +x warm 
arcf99-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_30e77291}
arcf99-picoctf@webshell:~$ 
```

## Notas adicionales

## Referencias



