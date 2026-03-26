# Norm of a matrix
## Aim
To write a program to find the 1-norm, 2-norm and infinity norm of the matrix and display the result in two decimal places.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
	1. Get the input matrix using np.array()   
    2. Find the 2-norm of the matrix using np.linalg.norm()
	3. Print the norm of the matrix in two decimal places.
## Program:
```
A = eval(input())

rows = len(A)
cols = len(A[0])

max_sum = 0

for j in range(cols):
    col_sum = 0
    for i in range(rows):
        col_sum += abs(A[i][j])
    if col_sum > max_sum:
        max_sum = col_sum

print("{:.2f}".format(max_sum))

```
```
A = eval(input())

m = len(A)
n = len(A[0])

ATA = [[0]*n for _ in range(n)]

for i in range(n):
    for j in range(n):
        s = 0
        for k in range(m):
            s += A[k][i] * A[k][j]
        ATA[i][j] = s

x = [1]*n

for _ in range(25):
    y = [0]*n
    for i in range(n):
        for j in range(n):
            y[i] += ATA[i][j] * x[j]
    norm = (sum(v*v for v in y))**0.5
    x = [v/norm for v in y]

num = 0
den = 0
for i in range(n):
    t = sum(ATA[i][j]*x[j] for j in range(n))
    num += x[i]*t
    den += x[i]*x[i]

lmax = num/den

print("{:.2f}".format(lmax**0.5))
```
```
A = eval(input())

max_sum = 0

for row in A:
    s = 0
    for v in row:
        s += abs(v)
    if s > max_sum:
        max_sum = s

print("{:.2f}".format(max_sum))
```
## Output:
<img width="668" height="260" alt="image" src="https://github.com/user-attachments/assets/13862d44-f3cd-4756-b96b-223f9cb633f1" />
<img width="772" height="292" alt="image" src="https://github.com/user-attachments/assets/6dc9ec63-1d9e-4e20-880c-7a252822eeed" />
<img width="642" height="246" alt="image" src="https://github.com/user-attachments/assets/025484b7-1cc7-434c-a415-ee8ecc92f499" />

### 1-Norm of a Matrix
<br>
<br>
<br>

### 2-Norm of a Matrix
<br>
<br>
<br>

### Infinity Norm of a Matrix
<br>
<br>
<br>

## Result
Thus the program for 1-norm, 2-norm and Infinity norm of a matrix are written and verified.
