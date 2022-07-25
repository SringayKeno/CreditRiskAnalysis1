# CreditRiskAnalysis1


## Overview of the analysis: Purpose of this analysis

This analysis takes a look at algorithms used to predict credit card risk. 

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, I oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Then, I used a combinatorial approach of over and undersampling using the SMOTEENN algorithm. Next, I d two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk.

## Results: 

### Using Resampling Models to Predict Credit Risk

#### Random Oversampling

In random oversampling, instances of the minority class are randomly selected and added to the training set until the majority and minority classes are balanced.

<img width="550" alt="1Naive Random Oversampling" src="https://user-images.githubusercontent.com/102890151/180676756-401f51d6-0292-4fc6-908f-95fa87ca84fb.png">


<img width="475" alt="2SMOTE Oversampling" src="https://user-images.githubusercontent.com/102890151/180676777-94373d5c-480e-4d06-a713-3f739a507426.png">



<img width="475" alt="3Undersampling" src="https://user-images.githubusercontent.com/102890151/180676797-d1c938af-5eea-4540-95e1-a30d62ff02be.png">

### Use the SMOTEENN Algorithm to Predict Credit Risk

<img width="450" alt="4Combination (Over and Under) Sampling" src="https://user-images.githubusercontent.com/102890151/180676819-7f8e6cb7-e06b-478c-9b68-afbc29f62781.png">

### Use Ensemble Classifiers to Predict Credit Risk

<img width="425" alt="7Balanced Random Forest Classifier" src="https://user-images.githubusercontent.com/102890151/180676839-70e3ef44-a694-45db-ae0f-14f47beff28f.png">

<img width="425" alt="7Balanced Random Forest Classifier2" src="https://user-images.githubusercontent.com/102890151/180676841-4fd0fcbe-6a6c-41c1-a407-5768a9dfd245.png">

<img width="331" alt="8Easy Ensemble AdaBoost Classifier" src="https://user-images.githubusercontent.com/102890151/180676855-9691eb92-2b59-44dc-8c72-3c923eaf603d.png">

<img width="331" alt="8Easy Ensemble AdaBoost Classifier2" src="https://user-images.githubusercontent.com/102890151/180676865-7cdc16a8-b6a0-4860-94d9-834d55f89163.png">




Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all six machine learning models. Use screenshots of your outputs to support your results.

## Summary: 

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning.
