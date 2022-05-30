<link rel="stylesheet" href="https://pyscript.net/alpha/pyscript.css" />
<script defer src="https://pyscript.net/alpha/pyscript.js"></script>

# Calculadorad de Area y Volumen

> Dado el radio de un cilindro este programa calculara la altura, area y volumen.

- Output
![demo](demo.gif = 100x20)



- Codigo

```python
# Copyright (c) 2022, by Tresillo
# All rights reserved.
# Licensed under the MIT license
# 5/30/2022 
import math
from tabulate import tabulate

class bcolors:
    HEADER = '\033[95m'
    OKBLUE = '\033[94m'
    OKCYAN = '\033[96m'
    OKGREEN = '\033[92m'
    WARNING = '\033[93m'
    FAIL = '\033[91m'
    ENDC = '\033[0m'
    BOLD = '\033[1m'
    UNDERLINE = '\033[4m'
    
nombres = ["", "Resultado", "Unidades"]
print(bcolors.HEADER, "Calculadora de Altura y Areas", bcolors.ENDC);

print(bcolors.OKCYAN, "Introduce el valor del radio: ", bcolors.ENDC);
radio = float(input(bcolors.OKBLUE))
print(bcolors.ENDC)

altura = 1000/(math.pi*pow(radio, 2))

area = (2*math.pi*pow(radio, 2))+(2*math.pi*radio*altura)

volumen = math.pi*pow(radio, 2) * altura

data = [
    ["Radio", '%.2f'%radio, "cm"],
    ["Altura", '%.2f'%altura, "cm"],
    ["Area", '%.2f'%area, "cm^2"],
    ["Volumen", '%.2f'%volumen, "cm^3"]
]

print(tabulate(data, headers=nombres, tablefmt="fancy_grid"))
```