Puntos: 50pts

# Objetivo del Nivel

How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 56491`

# Pistas del Nivel

- none

# Solución/Resultado/Flag

```bash
ryuuisdead-picoctf@webshell:~$ nc titan.picoctf.net 56491

Welcome to the Binary Challenge!

Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 11100000
Binary Number 2: 00101001


Question 1/6:
Operation 1: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 00100000             
Correct!

Question 2/6:
Operation 2: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11101001 
Correct!

Question 3/6:
Operation 3: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 00010100 
Correct!

Question 4/6:
Operation 4: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 100001001
Correct!

Question 5/6:
Operation 5: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 111000000
Correct!

Question 6/6:
Operation 6: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 00100000
Incorrect. Try again
Enter the binary result: 10001111100000
Correct!
Enter the results of the last operation in hexadecimal: 23E0

Correct answer!

The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_6862762d}

```

picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_6862762d}

# Notas Adicionales

# Referencias

https://play.picoctf.org/events/73/challenges?page=1&search=
