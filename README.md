# Dataset

This dataset contains 8732 labeled sound of urban sounds from 10 classes, you can download the files in the next url:

https://urbansounddataset.weebly.com/urbansound8k.html

# Objetive

The idea is to test different models using DeepLearning with Librosa for data preprocessing and feature extractions in order to identify the best model comparing DNN and CNN.

# Visual examples

Street music:
![Alt text](https://github.com/MLP5/DeepLearning-Urbansound/blob/main/Street_music.png)



# DNN

We use a DNN with the first hidden two layers with 258 and 128 nodes, the activation function will be 'relu' (we try with other for ex 'tanh' and 'relu' was the best figures), we use Dropout 20% to reduce the overfitting. 

The output layer has 10 nodes is label's number we have to classify. In this layer we use 'softmax' activation function.

After to run the model the train and test accuracy are the next:

Training Accuracy:  0.9939
Testing Accuracy:  0.9232

The loss function we use to compile is 'categorial_crossentropy' the best option for classification.

The optimizer will be 'adam'. It's a mixture in RMSprop and momentun with learning rate 'adaptative' into the optimizer.

The number of parameter with this model is 44682.

We fit the model with 150 epochs (we can reduce a little this number because the min loss is found before) and 30 batch_size.

The curves with the train and validation for accuracy and loss are the next. We see for both the adjust is very good with very very small overfitting.

![Alt text](https://github.com/MLP5/DeepLearning-Urbansound/blob/main/DNN.png)

# CNN

We use a CNN with the first hidden three layers with 64,64 and 128 nodes, the activation function will be 'relu' (we try with other for ex 'tanh' and 'relu' was the best figures), we use Dropout 20% to reduce the overfitting. We use 'BatchNormalization' to normalize the input to the activation function and 'MaxPooling2D' to reduce the number of parameters and the overfitting.

Before the output layer we include the 'Flatten' to modify the input to the last layer from tensor to vector with dim 1.

The output layer has 10 nodes is label's number we have to classify. In this layer we use 'softmax' activation function.

After to run the model the train and test accuracy are the next:

Training Accuracy:  0.99
Testing Accuracy:  0.86

The loss function we use to compile is 'categorial_crossentropy' the best option for classification.

The optimizer will be 'adam'. It's a mixture in RMSprop and momentun with learning rate 'adaptative' into the optimizer.

The number of parameter with this model is 153098.

We fit the model with 100 epochs (we can reduce a little this number because the min loss is found before) and 50 batch_size.

The curves with the train and validation for accuracy and loss are the next. We see for both the adjust is very good with very very small overfitting.

![Alt text](https://github.com/MLP5/DeepLearning-Urbansound/blob/main/CNN.png)
