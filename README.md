# LearningMachineLearning

## Overview
This is a repository to document my progress on learning basic machine learning concepts.

## Training Data
Fashion/Clothing Classification Tensorflow in-built training data (Fashion MNIST): tf.keras.datasets.fashion_mnist → https://www.tensorflow.org/tutorials/keras/classification
</br>
Text Classification/Sentinement Analysis training data (IMDB User Movie Reviews): https://ai.stanford.edu/~amaas/data/sentiment/
</br>
Linear Regression training data (UCI ML Repository): https://archive.ics.uci.edu/ml/datasets/Student+Performance
</br>
K-Nearest Neighbors training data (UCI ML Repository): https://archive.ics.uci.edu/ml/datasets/car+evaluation
</br>
Support Vector Machine sklearn in-built training data (Scikit Learn Dataset): datasets.load_breast_cancer() → https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_breast_cancer.html

## What I Learned
### Image Classification
##### Preparing Data
Image classification can be done usuing neural networks. In order to prepare the image data for classification, you can convert color images, if there are any, into black and white images. Each pixel of the black and white image will have a certain brightness level ranging from 0 to 255. Often times, you may want to work with smaller numbers, so it is better to later divide the brightness level by 255 to get a decimal between 0 and 1.
##### Model Architecture
Since the training data I used contained images that were 28 pixels by 28 pixels, the input layer can have 784 (28 times 28) neurons. I can add a hidden layer with an activation functions of relu to further optimize the network. Since there are 10 different outcomes the image can be, the output layer should have 10 neurons and I can use a softmax function. I made use of loss functions, which allows the computer to know how far the predicted outcome deviates from the actual outcome.
</br></br>
### Text Classification
##### Preparing Data
Simply explained, text classification works by mapping each word with to a numerical value. In order for the code to work for texts of different lengths, I can add tags such as UNUSED so that the computer knows to ignore those words. For example, if the number of words in a text is 700, and the arbitrary max number of words I had set was 1000, the computer will add 300 UNUSED tags to fill the rest of the spots up. Similar tags can be used for unknown words (UNK) and for padding characters (PAD).
##### Model Architecture
The neural network I used contained four layers. The input layer had 88000 neurons, which was the arbitrary number I chose for the max words. I has two hidden layers, one being a GlobalAveragePooling1D layer and another being a Dense layer. According to Tensorflow documentation, "GlobalAveragePooling1D layer returns a fixed-length output vector for each example by averaging over the sequence dimension. This allows the model to handle input of variable length, in the simplest way possible". The output layer has only 1 neuron. Using a sigmoid function as the activation function, the neuron will have a value that is either closer to 0 or 1 (0 being negative and 1 being positive). Based on this value of 0 to 1, the computer can differentiate between text with more negative words vs text with more positive words.
</br></br>
### Linear Regression
Linear Regression can be used to predict outcomes based on previous data. The computer essentially plots each data point on a graph (could be 2D or even 3D depending on how many parameters you have that are effecting the outcome). From the plotted points, the computer cna calculate a line of best fit. Using the line of best fit and basic data trends, the computer is able to predict an outcome. Linear regression, however, assumes that data is linearly correlated and my not always be as accurate. Sometimes, data can follow a curve, rather than a straight line. You can change the degree of the line by making it quadratic, cubic, quartic, etc. depending on what suites your data best. Aside from just the linear regression aspect of this project, I learn how I can save models without having to re-train it everytime I run it. This can be done using the pickle module, which sill save the data from the model into a pickle file. Later, I can simply open and load the file into the model. Matplotlib is also a helpful tool to visualize your data.
</br></br>
### K-Nearest Neighbors
K-Nearest Neighbors is an algorithm that can be used to predict the class a data point associates with. When data tends to clump into certain groups and you want to predict which group a certain point is part of, KNN comes handy. KNN locates the closest specified number of points within a certain range to a data point. Depending on the point afround it, the computer can predict which group the unknown point belongs in. For the data I worked with, finding the 9 closest neighbors worked the best for predicting unknown points. It is important to tweak this number depending on how your data is.
</br></br>
### Support Vector Machine
Description soon to be updated
</br></br>
### K-Means Clustering
Description soon to be updated
