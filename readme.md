### CNN INTRODUCTION
1) we use the log mel spectrogram as input to the first 2D convolutional layer.
The batch normalization layer after the feature extractor is used as a replacement for data standardization.

2) Each tensor between convolutional blocks has a shape of Fi × Ti × Ci, where
Fi - “the ith frequency size”
Ti is “the ith temporal size”
Ci is the number of channels. 

3) All input tensors after feature extraction have a shape of F0 × T0 × C0, where F0 = M = 128, T0 = Ts, and C0 = 1 .
We modify sizes of kernel, stride, and padding for the temporal dimension in few convolutional layers to make models faster.

### CNN - SM−W

1) sm - the decreasing temporal size parameter.
for sm > 0, temporal sizes Ti are reduced stronger based on increased stride sizes of convolutional layers hence reduce FLOPs of our models

2) W - the widening factor for the width of convolutional layers to change the computational complexity of models

### ARB OVERVIEW

ARB(x, y, c) is “the Audio Residual Block”, where x is the stride size for the frequency dimension,
y is the stride size for the temporal dimension, and c is the number of output channels.

Stride sizes si for i = 1,...,3 for convolutional blocks ARB(2, si, c) are calculated as
![stride size](/Images/stride_size.png)

Temporal sizes Ti for i = 0, . . ., 3 are calculated as 
![alt text](/Images/Temopral-size.png)

### AUDIO RESIDUAL BLOCK ARCHITECTURE
![alt text](/Images/ARB.png)

![alt text](/Images/ARB_Architecture.png)

### CNN ARCHITECTURE

![alt text](/Images/CNN_Architecture.png)
