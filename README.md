# Credit Risk Analysis

## Analysis Overview

In this project I trained and tested six different variations of a supervised machine learning model using a dataset of loan statistics from the year 2019. The six variations were oversampling (both random oversampling and SMOTE), undersampling  with the Cluster Centroids algorithm, the SMOTEEN combinatorial sampling aproach, the balanced random forest classifier, and the Easy Ensemble classifier. I ran a logistic regression with each of these approaches to predict loan status (either low risk or high risk) using a plethora of other factors as the regressors. I determined each variation's accuracy by running code to find a balanced accuracy socre, confusion matrix and imbalanced classification report.

## Results
NOTE: I consider a loan status of high risk a "positive" test when determining precision and recall.

### Random Oversampling

![BAS_ROS](https://user-images.githubusercontent.com/95651156/166171444-2070c946-246d-4d17-836a-52fbfdb77872.png)

![CR_ROS](https://user-images.githubusercontent.com/95651156/166171463-a69fae10-1c71-4799-a1a2-25307fb8260b.png)

The random oversampling algorithm produced a balanced accuracy score of 0.64, a precision of 0.01 and a recall of 0.66.

### SMOTE

![BAS_SMOTE](https://user-images.githubusercontent.com/95651156/166171729-9aecc3fa-b974-4d5d-ae61-68fc6e3d2dac.png)

![CR_SMOTE](https://user-images.githubusercontent.com/95651156/166171738-259ac111-f907-44c3-ab10-7353769c22bb.png)

The SMOTE algorithm produced a balanced accuracy score of 0.65, a precision of 0.01 and a recall of 0.64.

### Cluster Centroids

![BAS_CC](https://user-images.githubusercontent.com/95651156/166171932-fa806e5a-6bf4-41d8-8ef1-5ff4d71d3e40.png)

![CR_CC](https://user-images.githubusercontent.com/95651156/166171941-4271cad0-45f9-448c-b3cb-e57c6b1a48eb.png)

The cluster centroids algorithm produced a balanced accuracy score of 0.54, a precision of 0.01, and a recall of 0.69.

### SMOTEENN

![BAR_SMOTEENN](https://user-images.githubusercontent.com/95651156/166172017-e8e14e61-b563-4f26-99cf-bfe25ae0cc34.png)

![CR_SMOTEENN](https://user-images.githubusercontent.com/95651156/166172024-bf941497-c25f-4af5-ac64-800919738bc8.png)

The SMOTEENN algorithm produced a balanced accuracy score of 0.63, a precision of 0.01, and a recall of 0.68.

### Balanced Random Forest

![BAS_BRF](https://user-images.githubusercontent.com/95651156/166172160-48419f2e-8c44-4f57-9413-238e81660f1f.png)

![CR_BRF](https://user-images.githubusercontent.com/95651156/166172180-a1891ec9-1697-4890-8406-80020ff0e9dc.png)

The balanced random forest algorithm produced a balanced accuracy score of 0.79, a precision of 0.03, and a recall of 0.70.

### Easy Ensemble

![BAS_EE](https://user-images.githubusercontent.com/95651156/166172414-a50a944e-9810-435a-b094-2bfe65757ea9.png)

![CR_EE](https://user-images.githubusercontent.com/95651156/166172426-6daada37-a60b-4077-a717-423963b88754.png)

The easy ensemble algorithm produced a balanced accuracy score of 0.93, a precision of 0.09, and a recall of 0.92.

## Summary

### Top Takeaways

* Four of the six variations produced a precision score of 0.01, indicating that these models tend to predict false positives at an extremely high rate
* The balanced random forest and easy ensemlbe algorithms were slightly better at limiting the proportion of false positives to total predicted positives, producing precision scores of 0.03 and 0.09 respectively
* The balanced random forest and easy ensemlbe algorithms performed significantly better from both a balanced accuracy score and recall standpoint compared to the other four algorithms

### Reccomendation for Model

Each of the six models leave a lot to be desired when it comes to their precision scores, meaning that each model tends to produce false positives at a problematic rate. The good news is that, more likely than not, a false positive is not nearly as big of a problem as a false negative for whoever is trying to make a prediction on the status of a loan. In other words, detecting as many risky loans as possible while falsely labeling a large percentage of non-risky loans as risky is almost certainly better than doing the opposite. This is because the loan issuer does not get themselves in financial trouble by rejecting a high percentage of non-risky loans, but they do get themselves in trouble by accepting a high percentage of risky loans.

With the above discussion in mind, I argue that a model with a high recall score (True positives/(True Positives+False Negatives))is sufficent in this case, because it signals that the model fails to detect just a small percentage of risky loans. Therefore, I would reccomend utilizing the easy ensemble model to predict loan status because its recall score of 0.92 indicates that loan issuers can confidently use the model to detect 92% of risky loans.
