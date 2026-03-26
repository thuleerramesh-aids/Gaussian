# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
step 1: Start
Step 2: Input size
Read the number of unknowns n.
Step 3: Initialize matrices
Create an augmented matrix a of size n × (n+1) filled with zeros.
Create a solution array x of size n.
Step 4: Read matrix elements
Input all elements of the augmented matrix a[i][j].

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Thuleer R
RegisterNumber: 212225230285
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
n = int(input())


A = []
for i in range(n):
    row = []
    for j in range(n + 1):
        row.append(float(input()))
    A.append(row)


for i in range(n):
    for j in range(i + 1, n):
        ratio = A[j][i] / A[i][i]
        for k in range(n + 1):
            A[j][k] -= ratio * A[i][k]

x = [0 for _ in range(n)]

for i in range(n - 1, -1, -1):
    x[i] = A[i][n]
    for j in range(i + 1, n):
        x[i] -= A[i][j] * x[j]
    x[i] /= A[i][i]
    
for i in range(n):
    print(f"X{i} = {x[i]:.2f}", end=" ")

```

## Output:
<img width="623" height="814" alt="mfai 6" src="https://github.com/user-attachments/assets/b9d6e47d-aa14-440d-9396-2154cd738b28" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

