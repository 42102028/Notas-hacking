## Objetivo
This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: [VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/87e103a8db01087de9ccf5a7a022ddf8/VaultDoor1.java)

## Pistas
1. Look up the charAt() method online.


## Solución
picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_f6daf4}
```
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosPico/retosReversing/parte1/vaultDoor1]
└─$ wget https://jupiter.challenges.picoctf.org/static/87e103a8db01087de9ccf5a7a022ddf8/VaultDoor1.java       
--2024-04-19 23:53:05--  https://jupiter.challenges.picoctf.org/static/87e103a8db01087de9ccf5a7a022ddf8/VaultDoor1.java
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2264 (2.2K) [application/octet-stream]
Saving to: ‘VaultDoor1.java’

VaultDoor1.java              100%[=============================================>]   2.21K  --.-KB/s    in 0s      

2024-04-19 23:53:06 (10.1 MB/s) - ‘VaultDoor1.java’ saved [2264/2264]

                                                                                                                   
┌──(kali㉿kali)-[~/…/retosPico/retosReversing/parte1/vaultDoor1]
└─$ ls
VaultDoor1.java
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosPico/retosReversing/parte1/vaultDoor1]
└─$ open VaultDoor1.java       
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosPico/retosReversing/parte1/vaultDoor1]
└─$ MESA: error: ZINK: failed to choose pdev
glx: failed to create drisw screen
failed to load driver: zink
virtual KPtyProcess::~KPtyProcess() the terminal process is still running, trying to stop it by SIGHUP

                                                                                                                   
┌──(kali㉿kali)-[~/…/retosPico/retosReversing/parte1/vaultDoor1]
└─$ open VaultDoor1.java
                                                                                                                                                                                          
┌──(kali㉿kali)-[~/…/retosPico/retosReversing/parte1/vaultDoor1]
└─$ echo VaultDoor1.java 
VaultDoor1.java
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosPico/retosReversing/parte1/vaultDoor1]
└─$ cat VaultDoor1.java 
import java.util.*;

class VaultDoor1 {
    public static void main(String args[]) {
        VaultDoor1 vaultDoor = new VaultDoor1();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
    }

    // I came up with a more secure way to check the password without putting
    // the password itself in the source code. I think this is going to be
    // UNHACKABLE!! I hope Dr. Evil agrees...
    //
    // -Minion #8728
    public boolean checkPassword(String password) {
        return password.length() == 32 &&
               password.charAt(0)  == 'd' &&
               password.charAt(29) == 'a' &&
               password.charAt(4)  == 'r' &&
               password.charAt(2)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(3)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(1)  == '3' &&
               password.charAt(7)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(5)  == '4' &&
               password.charAt(9)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(8)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(6)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == '6' &&
               password.charAt(30) == 'f' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == 'd' &&
               password.charAt(26) == 'f' &&
               password.charAt(31) == '4';
    }
}
                                                                                                            
```

## Notas adicionales

## Referencias
https://medium.com/@arthDetroja/picoctf-write-up-vault-door-1-3076767a35b8




