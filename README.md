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
 
## Program to QR decomposition using the Gram-Schmidt method

Developed by: NIRANJAN P

RegisterNumber: 26006895

'''

import os

os.environ["OPENBLAS_NUM_THREADS"]= "1"

import numpy as np

def QR_Decomposition(A):

    # Write your code

    n,m=A.shape

    Q=np.empty((n,m))

    u=np.empty((n,m))

    u[:,0]=A[:,0]

    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])

    for i in range(1,m):

      
      u[:,i]=A[:,i]

      for j in range(i):

        u[:,i]-=(u[:,i] @ Q[:,j])*Q[:,j]

      Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])

    R=np.zeros((m,m))

    for i in range(m):

      for j in range(i,m):

          R[i,j]=A[:,j] @ Q[:,i]

    print("The Q Matrix is")

    print(f" {Q}")

    print("The R Matrix is")

    print(f" {R}")

a = np.array(eval(input()))

QR_Decomposition(a)








```

## Output

<img width="857" height="863" alt="image" src="https://github.com/user-attachments/assets/d8eb4271-0d73-42e4-ac0c-d937929732ad" />
<img width="870" height="745" alt="image" src="https://github.com/user-attachments/assets/07f996f5-1898-454a-90ef-ec95a35f4788" />




## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
