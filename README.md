# Credit_Risk_Analysis

![8-Credit Risk](https://user-images.githubusercontent.com/89308251/147290436-adcae2f9-8932-4c95-91f2-d9b2334520f1.jpg)


## Challenge Overview

### Purpose:

   The purpose of this analysis is to predict credit risk with machine learning models by using different techniques to train and evaluate models with unbalanced classes.
- **Resampling Models** 
	- **Over-sampling** method: using the **RandomOverSampler** & **SMOTE** algorithms
	- **Under-sampling** method: using the **ClusterCentroids** algorithm
	- **Combination Sampling** (a combinatorial approach of oversampling and undersampling): using the **SMOTEENN** algorithm
  
- **Ensemble Classifiers method**
	- using **BalancedRandomForestClassifier** & **EasyEnsembleClassifier** algorithms
  
 
## Resources
- Software:
   - Jupyter Notebook 6.4.6
   - Machine Learning
      - Python 
         - scikit-learn library
         - imbalanced-learn library
   
- Data source: 
   - Credit card credit dataset from LendingClub
      - [LoanStats_2019Q1.csv](https://github.com/SYDsCorner/Credit_Risk_Analysis/blob/main/Resources/LoanStats_2019Q1.csv)


## Results 

![1 Random_Oversampling](https://user-images.githubusercontent.com/89308251/147292939-c53ebebe-a386-4b51-8062-1780a32ef0c9.png)

- **Random Oversampling**
   - the balanced accuracy score: **66%**
   - the precision and recall scores (high_risk): 
      - The sensitivity/recall (71%) is more than the precision (1%) 
      - there are **many false positives** (predicted high risk but actually low risk)
      - making this a poor algorithm for this dataset
--------------------------------------------------------

![2 SMOTE ](https://user-images.githubusercontent.com/89308251/147292943-8b451544-8d70-49c6-b58e-6d4452643151.png)

- **Synthetic Minority Oversampling Technique (SMOTE)**
   - the balanced accuracy score: **66%**
   - the precision and recall scores (high_risk): 
      - The sensitivity/recall (63%) is more than the precision (1%) 
      - there are **many false positives** (predicted high risk but actually low risk)
      - making this a poor algorithm for this dataset

--------------------------------------------------------

![3 Undersampling_Cluster_Centroid](https://user-images.githubusercontent.com/89308251/147292947-778b0abb-04e4-45e4-8c5a-45c8f0dd4f31.png)

- **Cluster Centroid Undersampling**
   - the balanced accuracy score: **54%**
   - the precision and recall scores (high_risk): 
      - The sensitivity/recall (69%) is more than the precision (1%) 
      - there are **many false positives** (predicted high risk but actually low risk)
      - making this a poor algorithm for this dataset

--------------------------------------------------------

![4 Combination](https://user-images.githubusercontent.com/89308251/147292951-4ef55ca9-785a-49d5-bb8e-53e8d60a0566.png)

- **Combination Sampling With SMOTEENN**
   - The balanced accuracy score: **64%**
   - the precision and recall scores (high_risk): 
      - The sensitivity/recall (72%) is more than the precision (1%) 
      - there are **many false positives** (predicted high risk but actually low risk)
      - making this a poor algorithm for this dataset

--------------------------------------------------------

![5 Balanced_Random_Forest_Classifier](https://user-images.githubusercontent.com/89308251/147293771-ecebc676-9fcf-4025-bcf6-4228c302d987.png)

- **BalancedRandomForestClassifier**
   - The balanced accuracy score: **79%** 
   - the precision and recall scores (high_risk): 
      - The sensitivity/recall (70%) is more than the precision (3%) 
      - there are **many false positives** (predicted high risk but actually low risk)
      - making this a poor algorithm for this dataset
   - The **total_rec_prncp** and **total_pymnt** of the credit dataset are the more relevant features or columns
--------------------------------------------------------

![6 Easy_Ensemble_AdaBoost_Classifier](https://user-images.githubusercontent.com/89308251/147292985-993960db-c95b-42ca-b46e-a219ce0a8954.png)

- **EasyEnsembleClassifier**
   - The balanced accuracy score: **93%**
   - the precision and recall scores (high_risk): 
      - The sensitivity/recall (92%) is more than the precision (9%) 
      - there are **many false positives** (predicted high risk but actually low risk)
      - making this a poor algorithm for this dataset


## Summary:   

Eventhough the **EasyEnsembleClassifier** algorithm has the highest balanced accuracy score, 93%, this algorithm and the other algorithms still are not good enough to determine if a credit is high risk because the sensitivity/recall is very high, while the precision is very low. It indicates that there are **many false positives** (predicted high risk but actually low risk). Clearly, they are not useful algorithms for this dataset. Therefore I **would not recommend** that they be used to predict credit risk. Maybe a dataset with more obsevations would produce a better result.
