# XOR Gate using NN
#Activation function: Sigmoid
#Number of Hidden Layers:2


# XOR Gate using NN
#Activation function: Sigmoid
#Number of Hidden Layers:1

import numpy as np
def apply_net(y,w,b): 
    z=np.dot(y,w)+b 
    return(1/(1+np.exp(-z))) 
y_in=np.zeros((1,2)) 
w_in=np.array([[1.0], [1.0]]) 
b_in=1
y_in[0][0]=int(input("Input at first terminal: ")) 
y_in[0][1]=int(input("Input at second terminal: ")) 
a=apply_net(y_in,w_in,b_in)
y_1=np.zeros((1,2))
y_1[0][0]=a
y_1[0][1]=a
b1=0.0
if(0.82<apply_net(y_1,w_in,b1)<0.86):
    print("1")
else:
    print("0")
