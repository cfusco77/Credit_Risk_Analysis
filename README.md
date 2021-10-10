# Credit_Risk_Analysis
## Overview
Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. Therefore, we'll need to employ different techniques to train and evaluate models with unbalanced classes. Jill asks us to use imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.

Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, we'll oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Then, we'll use a combinatorial approach of over- and undersampling using the SMOTEENN algorithm. Next, we’ll compare two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. Once we’re done, we’ll evaluate the performance of these models and give a recommendation on whether they should be used to predict credit risk.

## Results
### Credit Resampling 
A. Native Random Sampling 

![Nativ_Random_Sampling](https://github.com/cfusco77/Credit_Risk_Analysis/blob/main/Resources/Native_Random_Oversampling.png) 

B. SMOTE Oversampling 

![Smote_Oversampling](https://github.com/cfusco77/Credit_Risk_Analysis/blob/main/Resources/SMOTE_oversampling.png)

C. Cluster Centroids Undersampling 

![Cluster_Centroids](https://github.com/cfusco77/Credit_Risk_Analysis/blob/main/Resources/Cluster_Centroids.png) 

D. Combination (Over and Under) Samping

![Combo_Sampling](https://github.com/cfusco77/Credit_Risk_Analysis/blob/main/Resources/combo_(over_under)_samping.png)

### Credit Ensemble 
E. Balanced Random Forest Classifier 

![Balanced_Random_Forest](https://github.com/cfusco77/Credit_Risk_Analysis/blob/main/Resources/Balanced_Random_Forest.png)

F. Easy Ensemble AdaBoost Classifier 

![Easy_Ensemble](https://github.com/cfusco77/Credit_Risk_Analysis/blob/main/Resources/Eady_Ensemble_adaBoost.png)

Summary: Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. If you do not recommend any of the models, justify your reasoning.
