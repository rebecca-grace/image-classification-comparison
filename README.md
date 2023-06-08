# Image Classification Comparison of Methods

### 1. Folder Structure

```python
Repository
 |-- classification_code.ipynb	# Main code notebook
 |    |-- input          # data inputs
 |    |    |-- train
 |    |    |    |-- images_training.h5           # model train dataset
 |    |    |-- test
 |    |    |    |-- images_testing.h5            # model test dataset
 |    |    |    |-- labels_testing_2000.h5       # image classification labels of test dataset
 |    |-- images          # for ReadMe file
```

### 2. Overview

In this project I will be running and comparing three classification methods K Nearest Neighbours, Naïve Bayes Algorithm and Multimonial Logistic Regression on the fashion MNIST image dataset.

The objective is to classify they gray scale images into one of the classes of clothing below

![method1](/images/method-1.png)

### 3. Methodology

The Naïve Bayes algorithm using bayes theorem to calculate the probability of a class given a test image. The predicted class is then the class that maximises the probability below.

![method2](/images/method-2.png)

Where P(class) is the prior from the train set, P(image|class) is the likelihood calculated from the training set which is assumed to be Gaussian. P(image) is the marginal probability, since the images are viewed to be independent which is the definition of Naïve Bayes, the denominator can be ignored.

The multinomial logistic regression works by converting the feature vectors (z) of the image into a probability vector using the softmax function below where k is each class label. 

![method3](/images/method-3.png)

Using this formula, we output probability values between 0 and 1. The algorithm then generates the predicted class based on the highest probability.

### 4. Results

Of the three algorithms considered the highest test prediction accuracy was generated from the Multinomial Logistic Regression with 83.90% accuracy, likely due to fine-tuned parameters.

Based on my results a probability-based measure is more effective than a distance-based algorithm, and parametric models performed better than the non-parametric KNN model. All 3 tested were supervised algorithms, it would be interesting to see how semi-supervised methods such as manifold learning or ensemble methods combining multiple algorithms.