# Neural_Network_Charity_Analysis

## Overview
The purpose of this project is to use deep-learning neural networks with the TensorFlow in Python to analyze and classify the success of charitable donations.
The methods used in the analysis are:
* Preprocessing the data for the neural network model  
* Compile, train, and evaluate the model  
* Optimize the model

### Tools used in this project
Jupyter Notebook

## Results
### Data Preprocessing
The first thing to do is to import the necessary dependencies. Next, the columns EIN and NAME are removed as they are not needed for the model.
The following columns are the features for our model:
* **APPLICATION_TYPE**
* **AFFILIATION**
* **CLASSIFICATION** 
* **USE_CASE**
* **ORGANIZATION**
* **STATUS**
* **INCOME_AMT**
* **SPECIAL_CONSIDERATIONS**
* **ASK_AMT**
  
Since the column **IS_SUCCESSFUL** contains binary data refering to wether the charity donation was used effectively, this variable will be considered the target for the deep learning neural network.  
After determining the features and target, the categorical variables are encoded, spliting into training and testing datasets and standardization have been applied to the features.

### Compiling, Training, Evaluating, and Optimizing the Model
![P1](https://user-images.githubusercontent.com/109183214/208974590-e1526541-c912-4a8b-96bb-c25bcfe9cd9c.png)
![P3](https://user-images.githubusercontent.com/109183214/208978964-00de6fee-cda2-413c-84f7-216e32954ad3.png)  
The deep-learning neural network model is made of two hidden layers with 80 and 30 neurons respectively. The input data has 43 features and 25,724 samples as shown from the `.shape`. To speed up the training process, the activation function ReLU is used for the hidden layers. Since the target is a binary classification, Sigmoid is used on the output layer. For the compilation, the optimizer is adam and the loss function is binary_crossentropy.  
![P4](https://user-images.githubusercontent.com/109183214/208979700-dde06a08-f11d-4204-9645-c301123506b6.png)  
The model's accuracy is just over 73% which doesn't help predict the outcome of the charity donations.

### Options to increase performance
To increase the performance of the model, bucketing was used on the feature ASK_AMT and organized the different values by intervals.
![P5](https://user-images.githubusercontent.com/109183214/208980682-eee0ed71-2b14-4fd1-af3e-70115e62450d.png)
![P2](https://user-images.githubusercontent.com/109183214/208980143-5bd6c20e-8b7d-422d-8ef3-ca0e9b88a8c4.png)

One of the ways thought of to get to the 75% model accuracy was by increasing the number of neurons on one of the hidden layers. However, that did not work.
![P6](https://user-images.githubusercontent.com/109183214/208983224-a63b1218-32eb-46d9-a24c-d8241c9049e2.png)
![P7](https://user-images.githubusercontent.com/109183214/208983227-33707405-faab-4ff0-9798-4b3fda3a9f55.png)

Next, a third hidden layer was added to the model, again that didn't work.
![P8](https://user-images.githubusercontent.com/109183214/208983311-d4ac57e0-9f0c-4450-b9ee-b755b4175391.png)
![P9](https://user-images.githubusercontent.com/109183214/208983312-94021387-b455-45ee-ae7f-9863b26e3cc5.png)

Lastly, a different activation function, tanh, was used. However, none of these steps helped improve the model's performance.
![P10](https://user-images.githubusercontent.com/109183214/208983818-a90420ee-a0b2-44f1-b0d6-422181b1ea48.png)
![P11](https://user-images.githubusercontent.com/109183214/208983820-a6d97195-417c-46f6-9960-93af47031a8c.png)

