# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

   ![Screenshot 2023-12-28 220056](https://github.com/ARAVIND23005370/QRdecomposition/assets/148514836/6360167a-56b8-4598-97ca-e0a5d272fbbd)


3.	Obtain the Q matrix
   
 ![Screenshot 2023-12-28 220105](https://github.com/ARAVIND23005370/QRdecomposition/assets/148514836/c49e418a-7707-4464-bba0-473f53b49bdb)


4.	Construct the upper triangular matrix R
   
![Screenshot 2023-12-28 220110](https://github.com/ARAVIND23005370/QRdecomposition/assets/148514836/b1c5069b-65f1-4bc7-8a4d-e496f675fb2c)




## Program:
### Gram-Schmidt Method
```PYTHON
import numpy as np
def QR_Decomposition(A):
      n,m=A.shape
      Q=np.empty((n,n))
      u=np.empty((n,n))
      u[:,0]=A[:,0]
      Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
      for i in range(1,n):
          u[:,i]=A[:,i]
          for j in range(i):
             u[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
             Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
      r=np.zeros((n,m))
      for i in range(n):
          for j in range(i,m):
              r[i,j]=A[:,j]@Q[:,i]
      print(Q)
      print(r)
a=np.array(eval(input()))
QR_Decomposition(a)
```

## Output
![Screenshot 2023-12-28 215503](https://github.com/ARAVIND23005370/QRdecomposition/assets/148514836/b8f9dbbd-28d9-4521-bc09-0e579621c797)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
