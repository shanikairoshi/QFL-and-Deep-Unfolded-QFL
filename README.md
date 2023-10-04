## Towards QFL with Deep-Unfolding Network
This repository comprises all the works related to the quantum federated aggregation strategy, applying novel strategies to enhance the aggregated model performance.

Study 01:
<img src="https://github.com/shanikairoshi/QFL-with-DUN/blob/main/Figures/QFLAggAnalysisTax.png" width="500"/>

Integrating quantum principles into well-established technical fields is an emerging area of focus.
Consequently, the field of federated learning has witnessed the emergence of quantum aspects, giving rise to what is known as quantum federated learning. In this research endeavour, our primary focus is a critical analysis of quantum federated aggregation and evaluating promising outcomes to enhance the aggregation task. Our principal objective involves the development of a qiskit-based environment tailored for the federated setting a feature that is currently unavailable followed by a meticulous examination of its applicability within federated contexts. Operating on the assumption that a simplified qubit structure, grounded in the reduced dimensionality of selected datasets, may yield favourable results within a constrained number of clients, our experimental approach is structured accordingly. Our findings demonstrate that the qiskit architecture can be effectively harnessed, subject to specific criteria, to improve Quantum Federated Learning (QFL) aggregation performance. Our objectives encompass enhancing our experiments and proposing optimal approaches to bolster performance. These include exploring novel gradient-free aggregation processes, optimization methods based on deep unfolding, and the management of diverse client contributions within supervised and unsupervised environments.
## Requirements

This code is implemented in 
Python 3.9, using qiskit qasm_simulator, matplotlib and numpy.

## System setup
<img src="https://github.com/shanikairoshi/QFL-with-DUN/blob/main/Figures/QFLsurveyVQC.png" width="500" />

01. We evaluate the VQC with different settings and federated aggregation.

Settings: 
    
    I). Change the optimizers in between COBYLA, SPSA, SLSQP, CMA-ES.
    
    II). Change the Circuit structure as TwoLocal, RealAmplitude, and EfficientSU2.
    
    III). Change the feature maps as zfeaturemap, zzfeaturemap, and paulifeaturemap.

## Pre-Processing

- Datasets
  
1. Mnist

The MNIST dataset has a total of 60,000 data points (rows in train_data) corresponding to digits ranging from 0 to 9 The first column has the label of the datapoint ranging from 0 to 9 The next 784 columns/features are each a 28x28 pixel grayscale image collapsed into a row. The dimension of the dataset is 784. Each of these values range from 0 to 255 where 0 corresponds to white and 255 corresponds to black and any value between 0 and 255 corresponds to a color which is a mix of black and white. The testing dataset has the same form except it has 10000 data points.

2. Fashion Mnist

Fashion MNIST is a dataset comprising 70,000 grayscale images, divided into training and testing sets of 60,000 and 10,000 images respectively, with each image representing a 28x28-pixel grayscale depiction of various fashion items, such as shoes, dresses, and trousers, among others

- Dimensionality Reduction
The dimension of the data corresponds to the number of qubits required in order to encode the data for the quantum feature maps. Since quantum computers today can only manipulate 50 qubits, we cannot work with large number of qubits like 784; therefore encoding data with dimension 784 is not viable.
Therefore, we will have to make use of the truncated Singular Value Decomposition (SVD) and t-distributed stochastic neighbor embedding (t-SNE) methods to reduce the dimension down to 10 and then to 2.

## Results
- Change the optimizers in between COBYLA, SPSA, SLSQP, CMA-ES.

<img src="https://github.com/shanikairoshi/QFL-with-DUN/blob/main/Figures/Optimizer.png" width="200" /> <figcaption align = "center"><b>Fig:1 Mnist Data</b></figcaption>
  
-Observation 1: COBYLA optimizer outperforms the SPSA optimizer significantly. We employed these two optimizers to assess gradient-based and gradient-free optimization settings, with SPSA representing the gradient-based approach and COBYLA representing the gradient-free method. Ultimately, our findings suggest that employing a gradient-free optimization protocol may yield superior global models in QFL aggregation for both of the datasets utilized in this study.


- Change the Circuit structure as TwoLocal, RealAmplitude, and EfficientSU2.

<img src="https://github.com/shanikairoshi/QFL-with-DUN/blob/main/Figures/CircuitMnist.png" width="200" /> <img src="https://github.com/shanikairoshi/QFL-with-DUN/blob/main/Figures/CircuitFashion.png" width="200" /> <figcaption align = "center"><b>Fig:2 Left figure shows results of mnist data and the right figure shows results of fashion mnist data</b></figcaption>
  
-Observation 2: We modified the circuit structure to evaluate the aggregation process, and our observations indicate that the EfficientSU@ circuit structure outperforms the other two methods, namely TwoLocal and RealAmplitude structures, for both experimental datasets.
  
- Change the feature maps as zfeaturemap, zzfeaturemap, and paulifeaturemap.

<img src="https://github.com/shanikairoshi/QFL-with-DUN/blob/main/Figures/CircuitAndFMMnist.png" width="200" /><img src="https://github.com/shanikairoshi/QFL-with-DUN/blob/main/Figures/CircuitAndFMFashion.png" width="200" /><figcaption align = "center"><b> Fig:3 Left figure shows results of mnist data and the right figure shows results of fashion mnist data</b></figcaption>
  
-Observation 3: when testing the feature maps, we found that the ZFeatureMap performs better compared to the other methods, including ZZFeatureMap and PauliFeatureMap.
## Usage
You can directly run these Python codes.

## Why Qiskit?
- <img src="https://github.com/shanikairoshi/QFL-with-DUN/blob/main/Figures/FrameworkDiff.JPG " />
## What next?
<img src="https://github.com/shanikairoshi/QFL-with-DUN/blob/main/Figures/QFLAggComponents.png"  width="500" /><figcaption align = "center"><b> Fig:4 Future Experimental Setup 01</b></figcaption>
We implement this similar phenomenon as shown in figure 5 into the quantum federated aggregation weighted mechanism to help in unbiased client selection procedure. Moreover, our target is to utilize the unrolling mechanism to develop a significant optimization strategy which may allow us to gain fast and accurate convergence in dynamic environment.

<img src="https://github.com/shanikairoshi/QFL-with-DUN/blob/main/Figures/DUN-QFL%20framworkV2.png"  width="500" /><figcaption align = "center"><b> Fig:5 Future Experimental Setup 02</b></figcaption>
<img src="https://github.com/shanikairoshi/QFL-with-DUN/blob/main/Figures/Algo1.JPG" width="500"/>

How does quantum federated aggregation handle missing data in a dynamic environment?
- Problem: Aggregation issues with dynamic and missing data can yield inaccurate global models,
causing detrimental decision-making, financial losses, and suboptimal resource allocation across various applications.
These challenges can dissuade organizations from adopting federated machine learning, hindering its potential for innovation.
Inefficient aggregation and scalability problems lead to high computational costs and slow convergence,
rendering federated learning impractical for large-scale applications.

- Hypothesis and Solutions: Our overarching objective is to progressively enhance existing research methodologies 
within the QFL framework by incorporating strategies for addressing the issue of missing data and promoting data reconstruction phenomena.
In this endeavor, we aim to bridge the gap between classical machine learning techniques and the unique requirements of quantum federated learning,
thereby contributing to the advancement of this emerging field.
<img src="https://github.com/shanikairoshi/QFL-with-DUN/blob/main/Figures/PhDRQ3.drawio.png" width="500"/>
<img src="https://github.com/shanikairoshi/QFL-with-DUN/blob/main/Figures/Algo2.JPG" width="500"/>

## Aknowledgement

Basic knowledge extracted from:

- https://www.qmunity.tech/tutorials/building-a-variational-quantum-classifier.
- https://www.youtube.com/watch?v=-sxlXNz7ZxU
