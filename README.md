# XOR Gate using NN
#Activation function: Sigmoid
#Number of Hidden Layers:2

import numpy as np
y_in=np.zeros((1,2))
y_1=np.zeros((1,2)) 
y_2=np.zeros((1,2)) 
y_3=np.zeros((1,2)) 
w_in=np.array([[-1.0], [-1.0]]) 
b_in=1
y_in[0][0]=int(input("Input at first terminal: ")) 
y_in[0][1]=int(input("Input at second terminal: ")) 
def nand(y,w,b):
    def apply_net(y,w,b): 
        z=np.dot(y,w)+b 
        return(1/(1+np.exp(-z)))   
    if(apply_net(y,w,b)>=0.5): 
        return("1") 
    else: 
        return("0")
y_1[0][0]=y_in[0][0]
y_1[0][1]=nand(y_in,w_in,b_in)
y_2[0][0]=nand(y_in,w_in,b_in)
y_2[0][1]=y_in[0][1]
y_3[0][0]=nand(y_1,w_in,b_in)
y_3[0][1]=nand(y_2,w_in,b_in)
print(nand(y_3,w_in,b_in))
