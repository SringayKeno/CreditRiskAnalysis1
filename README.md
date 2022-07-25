# CreditRiskAnalysis1


## Overview of the analysis: Purpose of this analysis

This analysis takes a look at algorithms used to predict credit card risk. 

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, I oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Then, I used a combinatorial approach of over and undersampling using the SMOTEENN algorithm. Next, I d two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk.

## Results: 

### Random Oversampling

In random oversampling, instances of the minority class are randomly selected and added to the training set until the majority and minority classes are balanced.

<img width="550" alt="1Naive Random Oversampling" src="https://user-images.githubusercontent.com/102890151/180676756-401f51d6-0292-4fc6-908f-95fa87ca84fb.png">

### SMOTE Oversampling

The synthetic Minority Oversampling (SMOTE) technique increases the size of minorities by interpolating new instances. That is, some nearest neighbours are selected for an instance of the minority class.

<img width="475" alt="2SMOTE Oversampling" src="https://user-images.githubusercontent.com/102890151/180676777-94373d5c-480e-4d06-a713-3f739a507426.png">

### Cluster Centroids Undersampling

Cluster Centroids identify majority class clusters and generate synthetic data points called centroids that represent the clusters. The majority class is then subsampled to the size of the minority class.

<img width="475" alt="3Undersampling" src="https://user-images.githubusercontent.com/102890151/180676797-d1c938af-5eea-4540-95e1-a30d62ff02be.png">


### SMOTEENN Combination Sampling

The SMOTEENN is a combination of the SMOTE algorithm and the Edited Nearest Neighbors (ENN) algorithm. SMOTEENN is a two-step process.
1. Oversample minority classes using SMOTE.
2. Use an undersampling strategy to clean up the resulting data. If the two nearest neighbors of a data point belong to two different classes, the data point will be deleted.

<img width="450" alt="4Combination (Over and Under) Sampling" src="https://user-images.githubusercontent.com/102890151/180676819-7f8e6cb7-e06b-478c-9b68-afbc29f62781.png">

### Random Forest Classifier

The random forest algorithm will sample the data and build several smaller, simpler decision trees. Each tree is simpler because it is built from a random subset of features.

<img width="425" alt="7Balanced Random Forest Classifier" src="https://user-images.githubusercontent.com/102890151/180676839-70e3ef44-a694-45db-ae0f-14f47beff28f.png">

<img width="425" alt="7Balanced Random Forest Classifier2" src="https://user-images.githubusercontent.com/102890151/180676841-4fd0fcbe-6a6c-41c1-a407-5768a9dfd245.png">

### Easy Ensemble Classifier

Easy Ensemble selects all examples from the minority class and a subset from the majority class to create a balanced sample of the training set. Instead of using a pruned decision tree, a boosted decision tree is used for each subset, especially the AdaBoost algorithm.

<img width="331" alt="8Easy Ensemble AdaBoost Classifier" src="https://user-images.githubusercontent.com/102890151/180676855-9691eb92-2b59-44dc-8c72-3c923eaf603d.png">

<img width="331" alt="8Easy Ensemble AdaBoost Classifier2" src="https://user-images.githubusercontent.com/102890151/180676865-7cdc16a8-b6a0-4860-94d9-834d55f89163.png">




Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all six machine learning models. Use screenshots of your outputs to support your results.

## Summary: 

Summary

* Out of all six machine learning models, SMOTEENN model has the lowest balanced accuracy score (51.0%) and Easy Ensemble AdaBoost Classifier model has the highest balanced accuracy score (92.5%). The balanced accuracy scores of the rest of the models are between 63.0% and 79.6%.

* All models have a 100% precision score for low risk loan, which means when the model predicts the credit risk is low for a loan, it is correct every time. But the precision scores for high risk loan for all models is very low (between 1.0% and 7.0%), meaning that all models are bad at predicting if a loan is actually a high risk one.

* The F1 sores (harmonic mean) of low risk loan is between 60.0% and 97.0% and this suggests the models handle the predictions for low risk loan well. However, the F1 scores for high risk loan varied between 1% and 14% and this means the success rate of recognizing a loan is risky is low.

* When evaluating if the machine learning model is good at predicting credit risk, we must bear in mind the dataset is heavily imbalanced (i.e. good loans outnumber risk ones). We cannot simply judge the models by its accuracy score and must review how well it predicts both low/high risk loans individually (by reviewing precision scores and F1 scores).
Compare to the ability to identify loans as low risk, the ability to flag high risk loans is more impactful as these loans have adverse impact to the company.

* All six models fail to predict credit risk, despite some models perform better than the others. Therefore, it is not recommended to use any of them alone to predict credit risk at this stage.
