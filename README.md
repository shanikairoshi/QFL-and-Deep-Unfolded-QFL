# QFL with Deep-Unfolding Network
This repository comprises all the works related to the quantum federated aggregation strategy, applying novel strategies to enhance the aggregated model performance.

--Methods--

01. We evaluate the VQC with different settings and federated aggregation.

Settings: 
    
    I). Change the optimizers in between COBYLA, SPSA,SLSQP, CMA-ES.
    
    II). Change the Circuit structure as TwoLocal, RealAmplitude, and EfficientSU2.
    
    III). Change the feature maps as zfeaturemap, zzfeaturemap, and paulifeaturemap.

--Datasets--

1. Mnist

The MNIST dataset has a total of 60,000 data points (rows in train_data) corresponding to digits ranging from 0 to 9 The first column has the label of the datapoint ranging from 0 to 9 The next 784 columns/features are each a 28x28 pixel grayscale image collapsed into a row. The dimension of the dataset is 784. Each of these values range from 0 to 255 where 0 corresponds to white and 255 corresponds to black and any value between 0 and 255 corresponds to a color which is a mix of black and white. The testing dataset has the same form except it has 10000 data points.

2. Fashion Mnist

Fashion MNIST is a dataset comprising 70,000 grayscale images, divided into training and testing sets of 60,000 and 10,000 images respectively, with each image representing a 28x28-pixel grayscale depiction of various fashion items, such as shoes, dresses, and trousers, among others

--Results--

--Evaluations--

-Why Qiskit?--

--What next?
