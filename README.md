# Maths-Assignment
import matplotlib.pyplot as plt
import numpy as np

noOfPlots1=50
harmonics=100

x=list(np.arange(-2*np.pi,2*np.pi+0.001,0.001))
period = 2*np.pi
def square(x):
    if x%period>0 and x%period<period/2:
        return 1
    else:
        return -1
def f(v):
    value=0;
    for x in range(harmonics):
        if x%2==1:
            value+= (4/(np.pi*x))*np.sin(x*v)
        
    return value
#for noOfPlots in range(1,noOfPlots1,2):
y=[] 
for i in x:
    y.append(square(i))
fig=plt.figure()
ax=fig.add_subplot(111)
ax.plot(x,y)
ax.axhline(0, color='black')

arr=[]
for i in x:
    arr.append(f(i))
ax.plot(x,arr)
plt.savefig('pakiaa'+str(50)+'.png')
