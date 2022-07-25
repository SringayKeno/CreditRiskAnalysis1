# CreditRiskAnalysis1


## Overview: Purpose of Analysis

This analysis takes a look at algorithms used to predict credit card risk. 

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, I oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Then, I used a combinatorial approach of over and undersampling using the SMOTEENN algorithm. Next, I look at two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk.

## Criteria

The following criteria are used to assess the model's performance.

* Accuracy Score - It is a number that denotes how accurate the prediction of the Machine learning model is. The actual formula is here: Accuracy_score = (True Positive+True Negative)/(True Positive +True Negative +False Positive +False Negative)

* Precision Score - Precision is one indicator of a machine learning model’s performance – the quality of a positive prediction made by the model. Precision refers to the number of true positives divided by the total number of positive predictions (i.e., the number of true positives plus the number of false positives).

* Recall Score - Recall, sometimes referred to as ‘sensitivity, is the fraction of retrieved instances among all relevant instances. A perfect classifier has precision and recall both equal to 1. It is often possible to calibrate the number of results returned by a model and improve precision at the expense of recall, or vice versa.

## Results: 

### Random Oversampling

In random oversampling, instances of the minority class are randomly selected and added to the training set until the majority and minority classes are balanced.

* The balanced accuracy score is 0.641
* Precision score - Precision score for high risk (0.01) and low risk 1.00
* Recall score - Recall score for high risk (0.60) and low risk 0.68 

below, the results of the random sampling algorithm

<img width="550" alt="1Naive Random Oversampling" src="https://user-images.githubusercontent.com/102890151/180676756-401f51d6-0292-4fc6-908f-95fa87ca84fb.png">

### SMOTE Oversampling

The Synthetic Minority Oversampling (SMOTE) technique increases the size of minorities by interpolating new instances. That is, some nearest neighbours are selected for an instance of the minority class.

* The balanced accuracy score is 0.637
* Precision score - Precision score for high risk (0.01) and low risk 1.00
* Recall score - Recall score for high risk (0.60) and low risk 0.68 

below, the results of the SMOTE Oversampling. There was very little difference between the SMOTE and random oversampling algorithms

<img width="475" alt="2SMOTE Oversampling" src="https://user-images.githubusercontent.com/102890151/180676777-94373d5c-480e-4d06-a713-3f739a507426.png">

### Cluster Centroids Undersampling

Cluster Centroids identify majority class clusters and generate synthetic data points called centroids that represent the clusters. The majority class is then subsampled to the size of the minority class.

* The balanced accuracy score is 0.637
* Precision score - Precision score for high risk (0.01) and low risk 1.00
* Recall score - Recall score for high risk (0.61) and low risk 0.45 

below the results for the undersampling

<img width="475" alt="3Undersampling" src="https://user-images.githubusercontent.com/102890151/180676797-d1c938af-5eea-4540-95e1-a30d62ff02be.png">


### SMOTEENN Combination Sampling

The SMOTEENN is a combination of the SMOTE algorithm and the Edited Nearest Neighbors (ENN) algorithm. SMOTEENN is a two-step process.
1. Oversample minority classes using SMOTE.
2. Use an undersampling strategy to clean up the resulting data. If the two nearest neighbors of a data point belong to two different classes, the data point will be deleted.

* The balanced accuracy score is 0.639
* Precision score - Precision score for high risk (0.01) and low risk 1.00
* Recall score - Recall score for high risk (0.70) and low risk 0.58 

results for the SMOTEENN Combination Sampling shown below

<img width="450" alt="4Combination (Over and Under) Sampling" src="https://user-images.githubusercontent.com/102890151/180676819-7f8e6cb7-e06b-478c-9b68-afbc29f62781.png">

### Random Forest Classifier

The random forest algorithm will sample the data and build several smaller, simpler decision trees. Each tree is simpler because it is built from a random subset of features.

* The balanced accuracy score is 0.788

<img width="425" alt="7Balanced Random Forest Classifier" src="https://user-images.githubusercontent.com/102890151/180676839-70e3ef44-a694-45db-ae0f-14f47beff28f.png">

* Precision score - Precision score for high risk (0.04) and low risk 1.00
* Recall score - Recall score for high risk (0.67) and low risk 0.91 

<img width="425" alt="7Balanced Random Forest Classifier2" src="https://user-images.githubusercontent.com/102890151/180676841-4fd0fcbe-6a6c-41c1-a407-5768a9dfd245.png">

### Easy Ensemble Classifier

Easy Ensemble selects all examples from the minority class and a subset from the majority class to create a balanced sample of the training set. Instead of using a pruned decision tree, a boosted decision tree is used for each subset, especially the AdaBoost algorithm.

* The balanced accuracy score is 0.925

<img width="331" alt="8Easy Ensemble AdaBoost Classifier" src="https://user-images.githubusercontent.com/102890151/180676855-9691eb92-2b59-44dc-8c72-3c923eaf603d.png">

* Precision score - Precision score for high risk (0.07) and low risk 1.00
* Recall score - Recall score for high risk (0.91) and low risk 0.94 

<img width="331" alt="8Easy Ensemble AdaBoost Classifier2" src="https://user-images.githubusercontent.com/102890151/180676865-7cdc16a8-b6a0-4860-94d9-834d55f89163.png">

## Summary: 

* Out of all six algorithms, the SMOTE (.0637) and Cluster Centriod (.0637) models the lowest balanced accuracy scores. The Easy Ensemble AdaBoost Classifier model has the highest balanced accuracy score (92.5%). The balanced accuracy scores of the rest of the models are between 63.9% and 78.8%.

* All the algorithms had hava 100% precision score for the low risk loan, which means when the model predicts the credit risk correct every time. The precision scores for high risk loans for all models was very low (between 1.0% and 7.0%) telling us that all the algorithms are bad at predicting if a loan is high risk.

* The best model that performed was the Easy Ensemble AdaBoost Classifier with a balanced accuracy score of 92.5% and the highest precision score of 7% among the algorithms accessed and high sensitivity score of 91%.

* All six models failed to predict high credit risk, despite some models performing better than others. It is not recommended to use any of them alone to predict credit risk at this stage.
