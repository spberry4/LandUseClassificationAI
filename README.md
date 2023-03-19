# Project Name: Land Usage Classification AI

## Requirements

```python
import earthpy.plot as ep
import earthpy as et
import earthpy.spatial as es
import tensorflow as tf
from tensorflow import keras
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from google.colab import drive
import seaborn as sns
from sklearn.model_selection import train_test_split
from scipy.io import loadmat
```

## Project Description

Land Usage classification is extremely important in our ever evolving world to keep track on how people/companies are using land and to monitor global land usage for science. The data comes from the JPL project AVIRIS which consists of 224 bands of hyperspectral imagery. This type of data can be used to determine many different things including identifying vegetation, determining agricultural uses, snow and ice coverage, and ground atmospheric data. This type of data is only increasing in volume therefore automatic classification can save time and be more efficient. The use of a Convolutional Neural Net has become commonplace when classifying images and can be used in this case to accurately identify the different land classes.

## Model Archicture

A convolutional neural network was used in order to classify the data. Tensorflow was used to build this network. A convolution works by reducing the size of the image and scaling down the image in order to identify important features and use those features to determine a classification. Below is the archicture used for this classifier:

- Convolutional Layer (Input Layer)
- Convolutional Layer
- Convolutional Layer
- Max Pooling
- Batch Normalization
- Convolutional Layer
- Convolutional Layer
- Convolutional Layer
- Max Pooling
- Batch Normalization
- Convolutional Layer
- Convolutional Layer
- Convolutional Layer
- Flattening
- Dense
- Dropout
- Dense
- Dropout
- Dense (Output Layer)

An activation function of SELU was used for this which stands for Scaled Exponential Linear Unit. This function was first introduced in 2017 which is a variant of the ELU function but allows for self normalization which maintains a mean of 0 and a standard deviation of 1. There are a few caveats though where a lecum_normal initializer must be used and the network has be be sequential. This function helps prevent exploding or vanishing gradients within the system, this is further controlled using batch normalization. Dropout layers were also added to the dense layers in order to introduce randomness into the system with a 40% probability of dropping neurons from the network. The output layer has 18 neurons for the 18 different classes available and a softmax activation is used. 

## Model Baselines

The model was trained on 38,303 observations and achieved a 91% accuracy rating. The model was then validated on 5,000 observations and achieved approximately 92% accuracy with the validation data. The closeness of these two accuracy ratings indicated that the model is not overfitting and will generalize well with any new data that is read into the model. 

## Model Performance and Conclusion

On 10,826 observations the testing data achieved a 92% accuracy. While accuracy tells us about the overall accuracy of the model we can delve deeper into the accuracy using a confusion matrix. See below for the confusion matrix:

![confusion matrix](https://user-images.githubusercontent.com/95090904/182252064-8eb10d6a-dc78-40fb-94bf-4ea85af430fe.png)

We can clearly see that the model does a great job at classifying almost all the different classes except for 15 and 8 which are grapes and a vineyard. These two are very similar to each other so it's no surprise that this is happening. Further training would be needed to correct this but an accuracy of 92% is already quite high therefore this may not be needed.

Additional Info:

Data retrieved from AVIRIS and can be located here:

http://www.ehu.eus/ccwintco/uploads/a/a3/Salinas_corrected.mat 
http://www.ehu.eus/ccwintco/uploads/f/fa/Salinas_gt.mat
