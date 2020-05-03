Convolutional neural network problems


1.	Cat_dog_cnn
Binary classification problem( cat vd dog) based on 3 convolutional layers with 32 and 64 filters. The first dense contains of 64 neurons with 1183808 parameters. As a result we have only one neuron, which indicates binary classification (Dog or Cat).
Final result: Loss : 54 % Accuracy: 74%

2.	Imagenet
Image class prediction based on Imagenet dataset (ResNet50)

3. MNIST

MNIST – black and white images constructed by NIST’s which contain binary images of handwritten digits written by high school students and employees of the United States Census Bureau. Very popular and most basic dataset in the field of image processing system.  The dataset is normalized to fit 28x28 pixel bounding box

You can download the dataset from  keras.datasets library (mnist).  There are 60000 samples for training and 10000 samples for test set. The image has got 28 x 28 pixels.
Firstly, you need to convert X_train/X_test to a digestable format by CNN (add an RGB canal). For the purpose of this exercise I will use only one RGB (keeping our images gray) to avoid  overfitting.
I will use keras build-in backend function to add one more dimension. After transformation X_train/X_test would look like this: 
(60000, 28, 28, 1) (10000, 28, 28, 1)

One last step in data preparation is to normalize X_train/X_train and convert y_train/y_test to a categorical values. There are 10 expected categories (num_classes) in the end.

I will start from the basic architecture, slowly  increasing the complexity. The goal is to compare final result and check how does the architecture advancement affects the result. 

Let’s try the following options:
1.	Simple cnn() – Conv2D + MaxPool2D and Dropout
2.	Doubled cnn() –  Conv2D + Conv2D + MaxPool + Dropout
3.	Third cnn() – three layers (Conv2D + Conv2D + MaxPool + Dropout)
4.	Check where the model is wrong
5.	Try hyperopt parameter optimisation to squeeze even more
6.	Try to address the question: does it makes any sens to apply “Transfer Learning” with VGG16 on such a simple dataset?

To evaluate my  neural network  I wil use accuracy and category_crossentropy as an external success metric and internal success metric respectively.



