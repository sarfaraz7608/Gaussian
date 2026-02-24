# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
## Step 1:

Import the numpy and sys modules to perform matrix operations and handle divide-by-zero errors.

## Step 2:

Read the number of unknowns and create an augmented matrix using np.zeros().
Accept all matrix elements from the user.

## Step 3:

Apply forward elimination to convert the augmented matrix into an upper triangular matrix using row operations.

## Step 4:

Perform back substitution to calculate the values of unknown variables starting from the last equation.

## Step 5:

Display the solution of each variable (X0, X1, X2, …) rounded to two decimal places and end the program.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: SARFARAZ I
RegisterNumber: 212225230252
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1),dtype=float)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x=np.zeros(n) 
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    if i==0:
        print("X%d = %.2f" % (i,x[i]),end="")
    else:
        print(" X%d = %.2f" % (i,x[i]),end="")
*/
```

## Output:
![alt text](<Screenshot 2026-02-24 200127.png>)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

