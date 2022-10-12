# Predictive-Maintenance-using-Random-Forest

# 1. Business Framing & Project overview

## Background
Manufacturing equipment / machineries are often used without a planned to maintenance. Such strategies often result in unexpected downtime due to unexpected failures. Planned maintenance often replaces components to avoid unexpected equipment failures, but increases downtime and maintenance costs. The emergence of Industry 4.0 and Artificial intelligent has increased focus on predictive maintenance (PdM) strategies that can reduce the cost of downtime and increase the availability (uptime) of manufacturing assets. PdM also has the potential to promote sustainable manufacturing practices by maximizing the useful life of components.

This project is approach of Machine learning implementation (Random Forest) for Predictive Maintenance.

## Dataset source information
Dataset source from UCI link here: https://archive.ics.uci.edu/ml/datasets/AI4I+2020+Predictive+Maintenance+Dataset

## Objective
This project is try to answer below business question:
1. What is the most suitable Random Forest model that fit for Predictive Maintenance reperesent by dataset?
2. What is features/attribute the model ‘thinks’ are most important in determining failure of the machine?

# 2. Data understanding

Feature information:
*   `UDI`: unique identifier ranging from 1 to 10000.
*   `Product ID`: Product Identification number.
*   `Type`: consisting of a letter L, M, or H for low (50% of all products), medium (30%), and high (20%) as product quality variants and a variant-specific serial number.
*   `Air temperature [K]`: generated using a random walk process later normalized to a standard deviation of 2 K around 300 K.
*   `Process temperature [K]`: generated using a random walk process normalized to a standard deviation of 1 K, added to the air temperature plus 10 K.
*   `Rotational speed [rpm]`: calculated from powepower of 2860 W, overlaid with a normally distributed noise.
*   `Torque [Nm]`: torque values are normally distributed around 40 Nm with an Ïƒ = 10 Nm and no negative values.
*   `Tool wear [min]`: The quality variants H/M/L add 5/3/2 minutes of tool wear to the used tool in the process. and a 'machine failure' label that indicates, whether the machine has failed in this particular data point for any of the following failure modes are true.
*   `Target`: Categorixe condition of the Machine = Failure or Not.
*   `Failure Type`: Type of Failure, there are tool wear failure (TWF), Heat Dissipation Failure (HDF), Power Failure (PWF), Overstrain Failure (OSF), Random Failures (RNF).


# 3. Perform Exploratory Data Analysis
![image](https://user-images.githubusercontent.com/114860846/195148626-0bc35828-a389-4d7e-a23a-1a062a38e607.png)

1. The true continuous numeric features: `Air temperature [K]`, `Process temperature [K]`,`Rotational speed [rpm]`, `Torque [Nm]` & `Tool wear [min]` which  is good (no need to transform them to approximate normal distribution).
2. In terms of the target variable, `Target = 0` is more frequent in the dataset. But, the imbalance condition is NOT severe (still OK).

![image](https://user-images.githubusercontent.com/114860846/195148793-b9de98ba-d69d-4825-8b6f-09e39c1476f0.png)

Let's say target = 1, means Failure, and admit_status = 0, means Not Failure
We can say that, machine with Low quality has more frequent to be Failure compare to High or Medium quality.


# 4. Random Forest Model 

## Classification Task Definition
TASK = To Predict Condition of Machine Failure or Not Failure

*   Failure = POSITIVE
*   No Failure =  NEGATIVE

*   TRUE POSITIVE = Predicted Failure, actual is Failure
*   TRUE NEGATIVE = Predicted No Failure, actual is No Failure
*   FALSE POSITIVE = Predicted Failure, actual is No Failure
*   FALSE NEGATIVE = Predicted No Failure, actual is Failure

Evaluation Metric:

    - PRECISSION = TP/(TP+FP)

    - RECALL = TP/(TP+FN)

    - F1 SCORE = 2 * (precision * recall)/(precision + recall)

    - ROC AUC
    
 ## Create  Model
 - Base Model
 - Undersampling Model
 - Oversampling Model
 - Combine Model
 
# 5. Evaluation, Choose The Best Model & Check Feature Importance

## Model with highest Accuracy
Model with highest Accuracy configuration : 
*   oversampled coef = 0.1
*   undersampled coef = 0.1

## Model with highest Precission
Model with highest Precission configuration : 
*   oversampled coef = 0.1
*   undersampled coef = 0.1

## Model with highest F1 Score
Model with highest F1 Score configuration : 
*   oversampled coef = 0.1
*   undersampled coef = 0.1

## Model with highest Recall
Model with highest Recall configuration : 
*   oversampled coef = 0.1
*   undersampled coef = 0.6

## Feature Importance Check
Top 3 Feature Importance of this Random Forest model are `Torque [Nm]`, `Air temperature [K]` & `Process temperature [K]`.


# 6. Conclusion
Best Random Forest model for this project is Combine Undersampling & Oversampling method (with higest RECALL score)
Model configuration: 
*   oversampled coef = 0.1
*   undersampled coef = 0.6  

Top 3 Feature Importance of this Random Forest model are:
- `Torque [Nm]`, 
- `Air temperature [K]`  
- `Process temperature [K]`

# Credit & Acknowledgement for dataset source:
Dua, D. and Graff, C. (2019). UCI Machine Learning Repository [http://archive.ics.uci.edu/ml]. Irvine, CA: University of California, School of Information and Computer Science.

