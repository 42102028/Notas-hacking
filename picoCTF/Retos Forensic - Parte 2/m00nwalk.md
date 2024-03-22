## Objetivo
Decode this [message](https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav) from the moon.

## Pistas
1. How did pictures from the moon landing get sent back to Earth?
2. What is the CMU mascot?, that might help select a RX option

## Solución
```
┌──(kali㉿kali)-[~/Documents/retosForensic/moonwalk]
└─$ sstv -d message.wav   
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...   [##########################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                            
┌──(kali㉿kali)-[~/Documents/retosForensic/moonwalk]
└─$ ls
message.wav  result.png
                                                                            
┌──(kali㉿kali)-[~/Documents/retosForensic/moonwalk]
└─$ open result.png 
                                                                            
┌──(kali㉿kali)-[~/Documents/retosForensic/moonwalk]
└─$ 

```

## Notas adicionales

## Referencias



