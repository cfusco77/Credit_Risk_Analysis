# Credit_Risk_Analysis
## Overview
Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Therefore, we'll need to employ different techniques to train and evaluate models with unbalanced classes. Jill asks us to use imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, we'll oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Then, we'll use a combinatorial approach of over- and undersampling using the SMOTEENN algorithm. Next, we’ll compare two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. Once we’re done, we’ll evaluate the performance of these models and give a recommendation on whether they should be used to predict credit risk.

## Definitions 
Precision: Precision is the measure of how reliable a positive classification is. \
Recall: Recall is the ability of the classifier to find all the positive samples. \
F1: F1 score is a weighted average of the true positive rate (recall) and precision, where the best score is 1.0 and the worst is 0.0 

## Results
### Credit Resampling 
A. Native Random Sampling: In random oversampling, instances of the minority class are randomly selected and added to the training set until the majority and minority classes are balanced. The Python implementation is simple. 

![Nativ_Random_Sampling](https://github.com/cfusco77/Credit_Risk_Analysis/blob/main/Resources/Native_Random_Oversampling.png) 

Accuracy Score: .638 \
Precision: High Risk .01 | Low Risk 1.00 \
Recall: High Risk .66 | Low Risk .61 

B. SMOTE Oversampling: The synthetic minority oversampling technique (SMOTE) is another oversampling approach to deal with unbalanced datasets. In SMOTE, like random oversampling, the size of the minority is increased. In SMOTE, new instances are interpolated. That is, for an instance from the minority class, a number of its closest neighbors is chosen. Based on the values of these neighbors, new values are created.

![Smote_Oversampling](https://github.com/cfusco77/Credit_Risk_Analysis/blob/main/Resources/SMOTE_oversampling.png)

Accuracy Score: .659 \
Precision: High Risk .01 | Low Risk 1.00 \
Recall: High Risk .62 | Low Risk .69

C. Cluster Centroids Undersampling: Cluster centroid undersampling is akin to SMOTE. The algorithm identifies clusters of the majority class, then generates synthetic data points, called centroids, that are representative of the clusters. The majority class is then undersampled down to the size of the minority class.

![Cluster_Centroids](https://github.com/cfusco77/Credit_Risk_Analysis/blob/main/Resources/Cluster_Centroids.png) 


Accuracy Score: .544 \
Precision: High Risk .01 | Low Risk 1.00 \
Recall: High Risk .69 | Low Risk .40

D. Combination (Over and Under) Samping: SMOTEENN combines the SMOTE and Edited Nearest Neighbors (ENN) algorithms. SMOTEENN is a two-step process:
1. Oversample the minority class with SMOTE.
2. Clean the resulting data with an undersampling strategy. If the two nearest neighbors of a data point belong to two different classes, that data point is dropped.


![Combo_Sampling](https://github.com/cfusco77/Credit_Risk_Analysis/blob/main/Resources/combo_(over_under)_samping.png)

Accuracy Score: .648 \
Precision: High Risk .01 | Low Risk 1.00 \
Recall: High Risk .72 | Low Risk .57

### Credit Ensemble 
E. Balanced Random Forest Classifier: Instead of having a single, complex tree like the ones created by decision trees, a random forest algorithm will sample the data and build several smaller, simpler decision trees

![Balanced_Random_Forest](https://github.com/cfusco77/Credit_Risk_Analysis/blob/main/Resources/Balanced_Random_Forest.png)

Accuracy Score: .789 \
Precision: High Risk .03 | Low Risk 1.00 \
Recall: High Risk .70 | Low Risk .87

F. Easy Ensemble AdaBoost Classifier: In AdaBoost, a model is trained then evaluated. After evaluating the errors of the first model, another model is trained. This time, however, the model gives extra weight to the errors from the previous model. The purpose of this weighting is to minimize similar errors in subsequent models.

![Easy_Ensemble](https://github.com/cfusco77/Credit_Risk_Analysis/blob/main/Resources/Eady_Ensemble_adaBoost.png)

Accuracy Score: .932 \
Precision: High Risk .09 | Low Risk 1.00 \
Recall: High Risk .92 | Low Risk .94

### Summary & Recommendation 
All of the modeling using resampling garnered the same precision scores and roughly the same accuracy scores. In summary, all of the models using resampling may not be the best for identifying high risk loans because the models' accuracies are low, and the precision and recall are not good enough to state that the model will be good at classifying high risk loans.

Both models using ensembling improved accuracy, precision and recall scores with Easy Ensemble AdaBoost Classfier method making the biggest improvement to the model's ability to predict high risk loans. 

Of the methods we explored I recommend Easy Ensemble AdaBoost Classifer but it is important to remember that modeling is an iterative process: we may need more data, more cleaning, another model parameter, or a different model to best predict high risk loans. 
