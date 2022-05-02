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
