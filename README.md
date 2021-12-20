# Gaussian Elimination with partial pivoting

## AIM:
To write a program to find the Gaussian Elimination with partial pivoting of a matrix.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import numpy and sys packages
2. Get the value of n for specifying number of rows
3. Declare a variable 'a' within numpy(zeros) package and range of n, n+1
4. Declare a variable "x" within numpy(zeros) package and range of n
5. Loop until i in the range of "n".
6. if "a" indexof i and index j==0.0 the execute the command sys.exit with statement Divide by zero detected.
7. loop until j in range of n
+1 declare ratio = a of index of j and index of i.
8. loop until k in range of n+1 and declare a[j][k]=a[j][k]-ratio*a[i][k]
9. declare x[n-1]=a[n-1][n]/a[n-1][n-1]
10. loop until i in the range of n-2,-1,-1 and declare x[i]=a[i][n]
11. loop until j in the range of i+1,n and declare x[i] =a[i][n]
12. declare x[i]=x[i]/a[i][i]
13. loop until i in the range n and display the result



 
 

## Program:
```
/*
Program to find the Gaussian Elimination with partial pivoting of a matrix.
Developed by: Souvik kundu
RegisterNumber: 21001557 
*/
import numpy as np
import sys
n = int(input())
a = np.zeros((n,n+1))
X = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by zero detected')
    for j in range(i+1, n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
X[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    X[i] = a[i][n]
    for j in range(i+1,n):
        X[i] = X[i] - a[i][j]*X[j]
    X[i] = X[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' %(i,X[i]), end = ' ')

```

## Output:
![gaussian elimination](fgh.png)


## Result:
Thus the program to find the Gaussian Elimination with partial pivoting of a matrix is written and verified using python programming.

