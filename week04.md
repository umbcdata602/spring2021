
# Week 4 -- Higher dimension (16 Feb)

In class, we'll investigate each of the classification models in Chapter 3, demonstrating and discussing:

* pros and cons of each algorithm
* hyperparameters and sensitivities
* relative performance with low dimensional datasets (Iris and make_blobs, see the assignment below)

We'll then add and implement concepts from Chapters 4 and 5, with special emphasis on

* data with higher dimension (wine dataset)
* feature selection
* dimensionality reduction (PCA)

Class discussions will involve working with code from the notebooks associated with Chapter 3, 4 & 5.
In particular, you should be familiar with the code in 
[ch04.ipynb](https://github.com/rasbt/python-machine-learning-book-3rd-edition/blob/master/ch04/ch04.ipynb) 
and [ch05.ipynb](https://github.com/rasbt/python-machine-learning-book-3rd-edition/blob/master/ch05/ch05.ipynb), 
and able to run these notebooks in Colab.

## Assignment

* Your code won't be collected. However, you should be ready to share your code in class. 
* Begin with [classification.ipynb](https://github.com/umbcdata602/spring2021/blob/master/classification.ipynb)
* Use the following code to create a dataset with `make_blobs`
* Perform this analysis for each of the following: Decision Tree, KNN, SVC, and Naive Bayes

```
from sklearn.datasets import make_blobs

std_true = 5.0    # original: 1.5
n_samples = 150   # original: 100

X, y = make_blobs(n_samples, 2, centers=2, random_state=2, cluster_std=std_true)
```

* Use the `train_test_split` method in scikit-learn to split the data with `test_size=0.3`
* Use the `StandardScaler` in scikit-learn to scale the data
* For each model, use the appropriate scikit-learn model to create and train a classifier.
    * Refer to week 3 reading assignment for guidance on the model you should use.
* Demonstrate overfitting and underfitting by plot the decision region and for different values of hyperparameters
* Use the confusion_matrix to help assess model performance.

## Reading

Make sure to look at associated Jupyter notebooks in github, and try running them in Google Colab.

* Rasckha & Mirjalili, Chapter 4: Building good training datasets
* Rasckha & Mirjalili, Chapter 5: Compressing data via dimensionality reduction

## Study guide for Week #4 quiz

* Curse of dimensionality
* Regularization -- L1 vs L2
* Scaling -- min/max vs zero mean/unit variance
* Feature selection -- greedy vs exhaustive algorithms
* High variance models -- the options
* Feature selection -- objectives
* Feature scaling -- min/max vs mean/variance
* Sequential feature selection algorithms -- pros and cons
* Feature importance with random forest -- pros and cons
* PCA -- role of covariance matrix
* Feature transformation and principal components
* LDA vs PCA
* Kernel PCA and the kernel trick
