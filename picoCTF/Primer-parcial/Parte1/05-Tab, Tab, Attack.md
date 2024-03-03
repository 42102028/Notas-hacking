## Objetivo
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/fe16c756149cfa85f23e73cd9dbd6a25/Addadshashanammu.zip)
## Pistas
After `unzip`ing, this problem can be solved with 11 button-presses...(mostly Tab)...

## Solución

La solución es:

1. Descomprimir el archivo `Addadshashanammu.zip`.
2. Navegar a través de los directorios anidados hasta llegar al archivo `fang-of-haynekhtnamet`.
3. Cambiar los permisos del archivo `fang-of-haynekhtnamet` para hacerlo ejecutable con `chmod +x`.
4. Ejecutar el archivo `fang-of-haynekhtnamet`.

Al ejecutarlo, se revela la flag

```
arcf99-picoctf@webshell:~/tab$ ls
Addadshashanammu.zip
arcf99-picoctf@webshell:~/tab$ unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
arcf99-picoctf@webshell:~/tab$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
arcf99-picoctf@webshell:~/tab/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls -l
total 12
-rwxr-xr-x 1 arcf99-picoctf arcf99-picoctf 8320 Mar 16  2021 fang-of-haynekhtnamet
arcf99-picoctf@webshell:~/tab/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ chmod +x fang-of-haynekhtnamet
arcf99-picoctf@webshell:~/tab/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ./fang-of-haynekhtnamet
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_76266e38}
arcf99-picoctf@webshell:~/tab/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ 
```

## Notas adicionales

## Referencias