# Credit_Risk_Analysis

## Overview of the analysis

Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Therefore, we’ll need to employ different techniques to train and evaluate models with unbalanced classes. We use imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.

* Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, we’ll oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. 
* Then, we’ll use a combinatorial approach of over- and undersampling using the SMOTEENN algorithm. Next, we’ll compare two new machine learning models that reduce bias,
BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. 
* We’ll evaluate the performance of these models and make a written recommendation on whether they should be used to predict credit risk.

## Results

1. Use Resampling Models to Predict Credit Risk.

Using your knowledge of the imbalanced-learn and scikit-learn libraries, you’ll evaluate three machine learning models by using resampling to determine which is better at predicting credit risk.

A. Random Oversampling

In random oversampling, instances of the minority class are randomly selected and added to the training set until the majority and minority classes are balanced.

![image](https://user-images.githubusercontent.com/111020934/206120634-a4e23de6-6a6b-4604-990d-713e74f32d8b.png)

![image](https://user-images.githubusercontent.com/111020934/206120702-20d91071-a4db-45f3-901d-832b10d6d939.png)

The accuracy score is low at around 64%, which states that the model was correct 64% of the time.

Precision: The precision for the high-risk loan applications is low, indicating a large number of false positives, which indicates an unreliable positive classification.

Recall:  A low recall is indicative of a large number of false negatives.

Support: For our results, there are 17118 actual occurrences for low-risk loans and 87 actual occurrences for high-risk loans.


Deliverable 2: Use the SMOTEENN Algorithm to Predict Credit Risk
Deliverable 3: Use Ensemble Classifiers to Predict Credit Risk
