# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Input matrix dimensions and initialize augmented matrix and solution vector.

2.Populate the augmented matrix with user inputs.

3.Perform Gaussian elimination to reduce the matrix to upper triangular form, ensuring no division by zero.

4.Back substitute to compute solution values for the variables.

5.Print the solution vector formatted to two decimal places.
## Program:
```
/*
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Hariprasad A
RegisterNumber: 2122252400048
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np

n = int(input())

a = []
for i in range(n):
    row = []
    for j in range(n + 1):
        row.append(float(input()))
    a.append(row)

a = np.array(a, dtype=float)

# Gaussian Elimination without partial pivoting
for k in range(n - 1):
    for i in range(k + 1, n):
        factor = a[i, k] / a[k, k]
        a[i, k:] = a[i, k:] - factor * a[k, k:]

# Back Substitution
x = np.zeros(n)

for i in range(n - 1, -1, -1):
    x[i] = (a[i, n] - np.dot(a[i, i+1:n], x[i+1:n])) / a[i, i]

for i in range(n):
    print(f"X{i} = {x[i]:.2f}", end=" ")
*/
```

## Output:
<img width="642" height="844" alt="Screenshot 2026-06-01 233742" src="https://github.com/user-attachments/assets/674bc87c-567e-4dc7-8afd-fa282ae45b93" />
<img width="519" height="296" alt="Screenshot 2026-06-01 233752" src="https://github.com/user-attachments/assets/a504eefa-cf61-40d8-89a4-f20fbd963cfc" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.




