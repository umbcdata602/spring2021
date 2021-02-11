
# Week 4 -- Higher dimension (16 Feb)

In class, continuing from last week, we'll investigate each of the classification models in Chapter 3, demonstrating and discussing:

* pros and cons of each algorithm
* hyperparameters and sensitivities
* relative performance with low dimensional datasets (Iris and make_blobs)

We'll then add and implement concepts from Chapters 4 and 5, with special emphasis on

* data with higher dimension (wine dataset)
* feature selection
* dimensionality reduction (PCA)

Class discussions will involve working with code from the notebooks associated with Chapter 3, 4 & 5.

## Assignment

This assignment focusses on KNN, will give you an idea of the discussion we'll have in class
for all the classification models.
Be ready to share your code in class, and to investigate similar questions related to the other models.

* Begin with [classification.ipynb](https://github.com/umbcdata602/spring2021/blob/master/classification.ipynb)
* Use the following code to create a dataset with `make_blobs`

```
from sklearn.datasets import make_blobs

std_true = 5.0    # original: 1.5
n_samples = 150   # original: 100

X, y = make_blobs(n_samples, 2, centers=2, random_state=2, cluster_std=std_true)
```

* Use the `train_test_split` method in scikit-learn to split the data with `test_size=0.3`
* Use the `StandardScaler` in scikit-learn to scale the data
* Use the `KNeighborsClassifier` class in scikit-learn to create and train a classifier. 
* Plot the decision region and investigate different values of K (overfitting and underfitting).
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
