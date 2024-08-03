# handwritten-digit-recognition
# Implementation and Comparison of various ML and CNN algorithms in detecting handwritten digits from Images

This mini-project is on recognition of Handwritten Digits and the original dataset is the MNIST handwritten digit dataset, which was taken from https://www.kaggle.com/competitions/digit-recognizer, which is part of a competition. The results are evaluated at the Kaggle website only. The goal of this project is simple -- to efficiently recognize as many handwritten digits as possible and compare the performance of various methods. This project was first started to solidify my theoretical learning, which gradually led to a sustained effort for improvement in accuracy. 

# Table of Contents

1. Import Libraries and Data

2. Standardization and PCA - we are chosing PCA because as we will see shortly, images of handwritten digits only vary in few central pixels. In other words, the pixels near the edges are all black and need not be taken into considerations. For instance, the images are (28 x 28) = 784 pixels and we will use 78 pixels (about 10% of the total) to predict the data.

3. Using K -nearest neighbor (KNN) classifier to predict the output

4. Using Decision Tree Classifier to predict the output -- comparison with the KNN classifier.

5. Using Support Vector Classifier (SVC) to predict the output -- comparison with the KNN and DT classifiers.

6. Use Convolutional Neural Networks to predict the labels -- we are using 2D convolutional kernels and BatchNormalization at every layer for better performance. We use two different optimizers to compare performance - adam and RMSprop - both of which have comparable performance. 

8. Conclusions:
   1. **Reasoning behind doing PCA** - Images of the Handwritten digits from MNIST digits, are more similar to one another than different. For instance, there are 28 x 18 = 784 pixels in each images, but most of those pixels are pitch black and do not contain any information about the digits. In other words, not all 784 features are relevant. 

   2. **Reasoning for choosing 78 Principal Components** - In light of the above, we used PCA for feature extraction. We made the choice that the information about the digit is stored in about 10% of the pixels. Hence, we isolated 78 principal components, after standardization, and projected the data onto these principal directions. 

   3. **Another reasoning for feature extraction** - Classification algorithms work better in lower-dimensional spaces (curse of dimensionality), when irrelevant and correlated features are eliminated. 

   4. **Classification** - We predicted the test data using three different classifiers : (a) KNN classifier (b) Decision Tree classifier and (3) Support Vector classifier (SVC). The test data contained 28000 different handwritten digits. 

   5. **Performance** - The SVC classifier worked the best with **98.03%** accuracy, whereas the DT classifier was clearly the worst with its accuracy theoretically bounded above by **86%**. The KNN classifier worked very well too with its accuracy **97.27%**. The best accuracy came from the CNN model (99% each with adam and RMSprop optimizer). 

   **The conclusion seems to be that both SVC and DT classifier work well for the purpose of recognizing handwritten digits from the MNIST dataset and the percentage accuracy for both of them is quite impressive. However, pushing the accuracy to its maximum is easier with CNN.**
 
