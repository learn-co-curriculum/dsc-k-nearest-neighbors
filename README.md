
# K-Nearest Neighbors

## Introduction

In this lesson, we'll learn about the supervised learning algorithm **_K-Nearest Neighbors_**, and how we can use it to make predictions for classification and regression tasks!

## Objectives

You will be able to:

* Implement a basic KNN Algorithm from scratch


### What is K-Nearest Neighbors?

**_K-Nearest Neighbors_** (or KNN, for short) is a supervised learning algorithm that can be used for both **_Classification_** and **_Regression_** tasks. KNN is a distance-based classifier, meaning that it implicitly assumes that the smaller the distance between 2 points, the more similar they are. In KNN, each column acts as a dimension. In a dataset with two columns, we can easily visualize this by treating values for one column as X coordinates and and the other as Y coordinates. Since this is a **_Supervised Learning Algorithm_**, we must also have the labels for each point in our dataset, or else we can't use this algorithm for prediction.  For simplicity's sake, we'll think only about classification problems throughout the remainder of this explanation. 

### Fitting the Model

KNN is unique compared to other classifiers in that it does almost nothing during the "fit" step, and all the work during the "predict" step. During the 'fit' step, KNN just stores all the training data and corresponding labels. No distances are calculated at this point. 

### Making Predictions with K

All the magic happens during the 'predict' step. During this step, KNN takes a point that we want a class prediction for, and calculates the distances between that point and every single point in the training set. It then finds the `K` closest points, or **_Neighbors_**, and examines the labels of each. You can think of each of the K-closest points getting a 'vote' about the predicted class. Naturally, they all vote for the same class that they are. The majority wins out, and the algorithm predicts the point in question as whichever class has the highest count among all of the k-nearest neighbors.

In the following animation, K=3.

<img src='knn.gif'>

### Distance Metrics

As we explored in a previous lesson, there are different **_distance metrics_** when using KNN. For KNN, we can use **_Manhattan_**, **_Euclidean_**, or **_Minkowski Distance_**--from an algorithmic standpoint, it doesn't matter which! However, it should be noted that from a practical standpoint, these can affect our results and our overall model performance. 

### Evaluating Model Performance

How we evaluate the model performance depends on whether we're using the model for a classification or regression task. KNN can be used for regression (by averaging the target scores from each of the K-nearest neighbors), as well as for both binary and mutlicategorical classification tasks. 

Evaluating classification performance for KNN works the same as evaluating performance for any other classification algorithm--we just need a set of predictions, and the corresponding ground-truth labels for each of the points we made a prediction on. We can then compute evaluation metrics such as **_Precision, Recall, Accuracy,_** and **_F1-Score_**. We will review these in detail later in this section. 
