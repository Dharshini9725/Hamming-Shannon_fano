# Exp:8 Hamming-Shannon-fano
# Name: Dharshini V S
# Reg no: 212223060050
# Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output.
# Apply the Huffman and Shannon-Fano to this source. Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.

### Aim:

To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.

### Tools Required:

python IDE with Numpy and Scipy.

### Program:
```python
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)

for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1

for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)

eff = hs / L
eff = round(eff,3)

red =  round(1 - eff,3) 

var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print()
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff*100} %")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```
### Calculation:

![image](https://github.com/user-attachments/assets/f5c5c469-56c2-4eef-9712-d35cc252c783)

![image](https://github.com/user-attachments/assets/9697b5b4-91b6-4e32-b941-bfc661eb4be6)

![image](https://github.com/user-attachments/assets/577d325c-47dd-4ba4-b829-860ee4120e2c)

![image](https://github.com/user-attachments/assets/2c2c3146-5dea-4d5c-a335-f44b2aca0660)

![image](https://github.com/user-attachments/assets/6a040e00-cd14-4f8b-9777-3a73c1870702)

### Result:
For the given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25 Average Codeword Length is : 2.625 Entropy is : 2.625 Efficiency is : 100.0 % Redudancy is : 0.0 Variance is : 0.484.






