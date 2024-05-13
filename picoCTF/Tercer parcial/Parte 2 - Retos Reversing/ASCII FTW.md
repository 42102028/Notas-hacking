## Objetivo
This program has constructed the flag using hex ascii values. Identify the flag text by disassembling the program.You can download the file from [here](https://artifacts.picoctf.net/c/506/asciiftw).

## Pistas
1. The combined range of hex-ascii for English alphabets and numerical digits is from 30 to 7A.
2. Online hex-ascii converters can be helpful.

## Solución
picoCTF{ASCII_IS_EASY_3CF4BFAD}

El script recorre un bloque específico de memoria del programa, extrae el segundo operando de cada instrucción en ese rango, lo convierte a un byte sin signo, y luego forma una cadena con estos bytes para mostrarla como una posible bandera (flag) del reto CTF.

```
En ghidra corremos este script 


from ghidra.program.model.mem import MemoryAccessException

start_addr = currentProgram.getAddressFactory().getAddress("00101184")
end_addr = currentProgram.getAddressFactory().getAddress("001011fc")

byte_list = []


current_addr = start_addr
while current_addr <= end_addr:
	instruction = getInstructionAt(current_addr)
	if instruction is not None:
		
		operand = instruction.getOpObjects(1)[0] # get second operand
		byte_val = operand.getValue() & 0xFF # convert to unsigned byte
		byte_list.append(byte_val)
                
       
        current_addr = current_addr.next()

flag = list(map(chr, byte_list))
print("Flag:", "".join(flag))
```

```
NewScript.py> Running...
('Flag:', 'picoCTF{ASCII_IS_EASY_3CF4BFAD}')
NewScript.py> Finished!
## Notas adicionales
```
## Referencias
[How To Crack PicoCTF ASCII FTW With Ghidra - StackZero](https://www.stackzero.net/picoctf-ascii-ftw/)



