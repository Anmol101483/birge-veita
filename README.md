Name- harshad
Roll No- SEL69
Date-13/02/2025

Program for Birge Vieta Method

Created on Thu Feb 13 14:36:06 2025

@author: harshad
"""

"Program For Birge Vieta Method"

import numpy as np

n=int(input("Enter the degree of equation\t"))

A=np.array([0.0 for i in range(n+1)])
B=np.array([0.0 for i in range(n+1)])
C=np.array([0.0 for i in range(n)])

for i in range(n+1):
    print("Enter value of coefficient x%d"%(n-i))
    A[i]=float(input())
        
iter=int(input("Enter no of iterations\t"))
p0=float(input("Enter the intial approx. of root\t"))

i=0
while(i<iter):
    print("Applying the %d iteration of Birge Vieta Method\n"%(i+1))
    B[0]=A[0]
    C[0]=B[0]
    j=1
    while(j<n+1):
        B[j]=A[j]+p0*B[j-1]
        j=j+1
        
    j=1
    while(j<n):
        C[j]=B[j]+p0*C[j-1]
        j=j+1
        
    p1=p0-(B[n]/C[n-1])
    
    print("The next approx. of root is",p1)
    
    p0=p1
    i=i+1
    
print("The iteration ended")
   
Output

Enter the degree of equation	3
Enter value of coefficient x3
1
Enter value of coefficient x2
-1
Enter value of coefficient x1
-1
Enter value of coefficient x0
1
Enter no of iterations	2
Enter the intial approx. of root	0.5
Applying the 1 iteration of Birge Vieta Method

The next approx. of root is 0.8
Applying the 2 iteration of Birge Vieta Method

The next approx. of root is 0.9058823529411766
The iteration ended
