# Credit_Risk_Analysis

## Overview of the analysis

Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Therefore, we’ll need to employ different techniques to train and evaluate models with unbalanced classes. We use imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.

* Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, we’ll oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. 
* Then, we’ll use a combinatorial approach of over- and undersampling using the SMOTEENN algorithm. Next, we’ll compare two new machine learning models that reduce bias,
BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. 
* We’ll evaluate the performance of these models and make a written recommendation on whether they should be used to predict credit risk.

## Results

### 1. Use Resampling Models to Predict Credit Risk.

Using our knowledge of the imbalanced-learn and scikit-learn libraries, we’ll evaluate three machine learning models by using resampling to determine which is better at predicting credit risk.

#### A. Random Oversampling

In random oversampling, instances of the minority class are randomly selected and added to the training set until the majority and minority classes are balanced.

![image](https://user-images.githubusercontent.com/111020934/206120634-a4e23de6-6a6b-4604-990d-713e74f32d8b.png)

![image](https://user-images.githubusercontent.com/111020934/206120702-20d91071-a4db-45f3-901d-832b10d6d939.png)

The balanced accuracy score is low at around 64%, which states that the model was correct 64% of the time.

Precision: The precision for the high-risk loan applications is low at 0.01, indicating a large number of false positives, which indicates an unreliable positive classification.

Recall:  For high-risk loans its 0.60 and for low-risk is 0.68. A low recall is indicative of a large number of false negatives.

Support: For our results, there are 17118 actual occurrences for low-risk loans and 87 actual occurrences for high-risk loans.

#### B. Synthetic Minority Oversampling Technique

The synthetic minority oversampling technique (SMOTE) is another oversampling approach to deal with unbalanced datasets. In SMOTE, like random oversampling, the size of the minority is increased.

![image](https://user-images.githubusercontent.com/111020934/206322763-25640125-3afc-46e2-aa6c-a5a8732a6eec.png)

![image](https://user-images.githubusercontent.com/111020934/206322818-fe69020e-da67-46d3-af89-6f1dc24f8347.png)

The balanced accuracy score is low at 63.7%.

Precision: The precision for the high-risk loan applications is low at 0.01.

Recall:  For high-risk loans its 0.60 and for low-risk is 0.68. A low recall is indicative of a large number of false negatives.

Support: For our results, there are 17118 actual occurrences for low-risk loans and 87 actual occurrences for high-risk loans.

#### C. Cluster Centroid Undersampling

Cluster centroid undersampling is akin to SMOTE. The algorithm identifies clusters of the majority class, then generates synthetic data points, called centroids, that are representative of the clusters. The majority class is then undersampled down to the size of the minority class.

![image](https://user-images.githubusercontent.com/111020934/206323988-3dbd95bc-4b57-4df1-9618-e3fc18e71e8e.png)

![image](https://user-images.githubusercontent.com/111020934/206324051-16793188-08e7-4b06-9a61-8e9c5f922e82.png)

The balanced accuracy score is low at 51.2%.

Precision: The precision for the high-risk loan applications is low at 0.01.

Recall:  For high-risk loans its 0.59 and for low-risk is 0.44. A low recall is indicative of a large number of false negatives.

Support: For our results, there are 17118 actual occurrences for low-risk loans and 87 actual occurrences for high-risk loans.

### 2. Use the SMOTEENN Algorithm to Predict Credit Risk

SMOTEENN combines the SMOTE and Edited Nearest Neighbors (ENN) algorithms. 

![image](https://user-images.githubusercontent.com/111020934/206324594-a9e62b31-e86a-4c8f-b53e-5af1465177b2.png)

![image](https://user-images.githubusercontent.com/111020934/206324674-906b7e40-7a26-4860-a47e-ca4132d8edca.png)

The balanced accuracy score is low at 62.4%.

Precision: The precision for the high-risk loan applications is low at 0.01.

Recall:  For high-risk loans its bit high at 0.70 and for low-risk is 0.68.

Support: For our results, there are 17118 actual occurrences for low-risk loans and 87 actual occurrences for high-risk loans.

### 3. Use Ensemble Classifiers to Predict Credit Risk

Using our knowledge of the imblearn.ensemble library, we’ll train and compare two different ensemble classifiers, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk and evaluate each model.

#### A. Balanced Random Forest Classifier

 A balanced random forest randomly under-samples each boostrap sample to balance it.
 
 ![image](https://user-images.githubusercontent.com/111020934/206325726-33dd618e-262e-45ae-b1f9-333673411ae5.png)

![image](https://user-images.githubusercontent.com/111020934/206325762-4e734f84-5b0c-4e1d-96e2-83381ffc257d.png)

The balanced accuracy score is high at 78.8%.

Precision: The precision for the high-risk loan applications is low at 0.04.

Recall:  For high-risk loans is 0.67 and for low-risk its high at 0.91.

Support: For our results, there are 17118 actual occurrences for low-risk loans and 87 actual occurrences for high-risk loans.

#### B. Easy Ensemble AdaBoost Classifier

The classifier is an ensemble of AdaBoost learners trained on different balanced boostrap samples. The balancing is achieved by random under-sampling. 

![image](https://user-images.githubusercontent.com/111020934/206326329-7be5de1b-34b3-451b-a417-9219890ef3c7.png)

![image](https://user-images.githubusercontent.com/111020934/206326379-6bb18fb2-89b6-46cc-9206-05cb73947c7e.png)

The balanced accuracy score is high at 92.5%.

Precision: The precision for the high-risk loan applications is low at 0.07.

Recall:  For high-risk loans is high at 0.91 and for low-risk its high at 0.94.

Support: For our results, there are 17118 actual occurrences for low-risk loans and 87 actual occurrences for high-risk loans.


## Summary

The balanced accuracy score is between 0 and 1 (0-100%) which states how often the model is good at prediction, the higher the better. Precision is the measure of how reliable a positive classification is and its value is between 0 and 1. A low precision is indicative of a large number of false positives.
Recall is the ability of the classifier to find all the positive samples. A low recall is indicative of a large number of false negatives.
F1 score is a weighted average of the true positive rate (recall) and precision, where the best score is 1.0 and the worst is 0.0.

If we look at the results of different resampling models (oversampling RandomOverSampler and SMOTE algorithms, the undersampling ClusterCentroids), the Cluster Centroid Undersampling model has a very low accuracy score of 51.2% and has low recall values(0.59/0.44) as well. This model may not be the best one for preventing fraudulent loan applications. The RandomOverSampler and SMOTE algorithms showed similar balanced accuracy score of around 64% and have optimum precision and recall values. These models are better in predicting the credit risk but not the best.

The Combination (Over and Under) Sampling model (SMOTEENN) report showed a similar balanced accuracy score (around 63%) but had high recall values (0.70/0.68) which states a low number of false negatives. But overall, this model too is not effective in predicting the credit risk.

The Balanced Random Forest Classifier has high balanced accuracy score of 78.8% and high recall values (0.67/0.91). This model is good at predicting the credit risk.
The Easy Ensemble AdaBoost Classifier has high balanced accuracy score of 92.5% and high recall values (0.91/0.94). This model is the best at predicting the credit risk due to its high accuracy in predicting correctly. The high recall value suggests very few false negatives.


