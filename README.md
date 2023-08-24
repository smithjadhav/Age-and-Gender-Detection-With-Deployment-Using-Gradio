 <h1> Age-and-Gender-Detection-With-Deployment-Using-Gradio </h1>
 
This project built a multi-output deep convolutional neural to classify the age, and gender of each image included in the UTK Face dataset, reaching an accuracy of 97.64 %.
To reduce overfitting, this project  
1.Added max-pooling layer and batch normalization between successive convolutional layers and dropout layer before each fully connected layer,  
2.Applied data augmentation, and  
3.Early stopping.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## 1.Dataset

<img width="800" alt="image" src="https://user-images.githubusercontent.com/74934323/102843052-64e93700-43d6-11eb-86fd-89eb02053abd.png">
The dataset this project used is the UTKFace dataset, which is released by UCI machine learning repository, and consists of over 20,000 face images with annotations of age, gender, and ethnicity. As shown in the picture above, although the images are properly cropped and only contain the face region, there are variations in pose, facial expression, and illumination. etc. among images, and thus this project thinks data augmentation is needed.     

  
For more information on this dataset please check [this website](http://aicip.eecs.utk.edu/wiki/UTKFace).

 
### 1.1 Distribution of Gender And Age
 
#### 1.1.1 Gender
 
<img width="450" alt="image" src="https://user-images.githubusercontent.com/74934323/102845400-7e40b200-43db-11eb-8c0b-37c2de6c7901.png">
 
  
#### 1.1.2 Age
  
<img width="450" alt="image" src="https://user-images.githubusercontent.com/74934323/102845312-4afe2300-43db-11eb-9c55-d45d8c18d6f8.png">
 
## 2 Strategies Applied for Reducing Overfitting


### 2.1 Max-pooling

When the training dataset is not large enough to contain all the features in the whole dataset, overfitting happens. By adding the max-pooling layer, the size of spatial size and the number of parameters will be reduced (et. only a subset of features which has the max value will be selected), as a result, the model is less likely to learn false patterns.


### 2.2 Batch Normalization

Regularization introduces additional information to the model and thus reduces the overfitting problem. One of the problems encountered often when training Deep Neural Networks is internal covariate shift, which is caused by the different distribution of each layer’s inputs. Luckily, batch normalization can avoid the problem by reducing the amount of hidden unit values shifting around. Also, each layer of the network can learn more independently from other layers 


### 2.3 Dropout 

One of the major challenges in training Deep Neural Networks is deciding when to stop the training. With too short time of training, underfitting occurs, while with too long time of training, overfitting occurs. This project will also apply early stopping to reduce overfitting – stop training when performance on the validation dataset starts to degrade


### 2.4 Data Augmentation

Data Augmentation reduces overfitting by enlarging the features in the training set and preventing the training model from learning false patterns. Data Augmentation has been used widely and has shown effective results in image classification 

Below is an example after applying data augmentation of one of the images in the dataset:

<img width="450" alt="image" src="https://user-images.githubusercontent.com/74934323/102846161-46d30500-43dd-11eb-86c5-39cc9264437d.png">



## 3 Model Architecture

<img src="https://github.com/smithjadhav/Age-and-Gender-Detection-With-Deployment-Using-Gradio/assets/40405066/acb303a9-eba2-41f3-a75f-a8e7b7c09b0e">

Model 1 has 5 convolutional layers, and 3 fully connected layers for each output.


## 4 Result

Below are the results predicted by model images : 

<img src="https://github.com/smithjadhav/Age-and-Gender-Detection-With-Deployment-Using-Gradio/assets/40405066/35016eb6-3641-4587-8efe-087fefb9b2b6">

