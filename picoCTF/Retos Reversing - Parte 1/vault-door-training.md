## Objetivo
Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility. The source code for the training vault is here: [VaultDoorTraining.java](https://jupiter.challenges.picoctf.org/static/03c960ddcc761e6f7d1722d8e6212db3/VaultDoorTraining.java)


## Pistas
1. The password is revealed in the program's source code.


## Solución
w4rm1ng_Up_w1tH_jAv4_3808d338b46
La ponemos en el formato picoCTF{w4rm1ng_Up_w1tH_jAv4_3808d338b46} y esa es la bandera 
```
┌──(kali㉿kali)-[~/…/retosPico/retosReversing/parte1/vaultDoorTraining]
└─$ java VaultDoorTraining.java
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: 
wqw     
Exception in thread "main" java.lang.StringIndexOutOfBoundsException: begin 8, end 2, length 3
        at java.base/java.lang.String.checkBoundsBeginEnd(String.java:4606)
        at java.base/java.lang.String.substring(String.java:2709)
        at VaultDoorTraining.main(VaultDoorTraining.java:9)
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosPico/retosReversing/parte1/vaultDoorTraining]
└─$ open VaultDoorTraining.java
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosPico/retosReversing/parte1/vaultDoorTraining]
└─$ MESA: error: ZINK: failed to choose pdev
glx: failed to create drisw screen
failed to load driver: zink

                                                                                                                   
┌──(kali㉿kali)-[~/…/retosPico/retosReversing/parte1/vaultDoorTraining]
└─$ java VaultDoorTraining.java
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: w4rm1ng_Up_w1tH_jAv4_3808d338b46
Access denied!
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosPico/retosReversing/parte1/vaultDoorTraining]
└─$ 

```


## Notas adicionales

## Referencias
https://medium.com/@arthDetroja/picoctf-write-up-vault-door-training-cb32f143decf




