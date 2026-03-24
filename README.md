# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
import numpy as np
def qr_decomposition(A):
    A=np.array(A,dtype=float)
    m,n=A.shape
    Q=np.zeros((m,n))
    R=np.zeros((n,n))
    for j in range(n):
        v=A[:,j]
        for i in range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            v=v-R[i,j]*Q[:,i]
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
    return Q,R
A=np.array(eval(input()))
Q,R=qr_decomposition(A)
print("The Q Matrix is\n",Q)
print("The R Matrix is\n",R)







```

## Output
```
<img width="1919" height="1002" alt="Screenshot 2026-03-24 192832" src="https://github.com/user-attachments/assets/52c7c028-d8cb-47f3-abce-78f76cd57b2a" />

```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
