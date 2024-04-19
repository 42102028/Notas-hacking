## Objetivo
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/c9593d1d2ac9d850da95bffe0ac3b6c6/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/c9593d1d2ac9d850da95bffe0ac3b6c6/scrambled2.png)

## Pistas
1. [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
2. Think of different ways you can "stack" images
## Solución
```
from PIL import Image
import numpy as np
import os

file_names = ["scrambled1.png", "scrambled2.png"]
img_data = [np.asarray(Image.open(f'{name}')) for name in file_names]

data = img_data[0].copy() + img_data[1].copy()

new_image = Image.fromarray(data)
new_image.save("out.png", "PNG")
```

Nos crea una imagen y ahi esta la bandera
## Notas adicionales

## Referencias
https://github.com/Dvd848/CTFs/blob/master/2021_picoCTF/Pixelated.md




