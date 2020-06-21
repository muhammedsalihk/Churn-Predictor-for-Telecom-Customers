# Churn Predictor for Telecom Customers

## Introduction
Customer churn is a strong concern for any company. This becomes even more stark in highly competetive industries like telecom where the customer acquisition costs can be pretty high.

And hence it becomes very important for companies to be able to predict beforehand the customers who might churn and thereafter preventing it by employing different customer retention strategies.

For companies with a large customer base, they would have enough data to build a good predictor for this. But a challenge here would be that this data would be inherently imbalanced as only a small fraction of the customers would churn usually.

Here we are trying to build a model for classifying telecom customers who would churn.

## Data Description
The dataset contains 20 features which includes some demographic information, account information and services that the customer has signed up for. It also provides information on customers who have churned in the last month.

The dataset contains records of 7043 customers, out of which nearly 27% of the customer have churned. This indicates that we have an imbalanced dataset at hand.

![Count Plot](https://github.com/muhammedsalihk/Churn-Predictor-for-Telecom-Customers/blob/master/Images/Image%201.png)

## Methodology
Since we have an imbalanced dataset, three sampling strategies were tried in order to create an efficient model.

    1. Using the original dataset
    2. Undersampling
    3. Oversampling using SMOTE

Before going ahead with the sampling, a detailed exploratory analysis was perfomed on the data and based on the inferences obtained, a set of relevant features were selected and some new features were engineered.

![EDA Sample](https://github.com/muhammedsalihk/Churn-Predictor-for-Telecom-Customers/blob/master/Images/Image%202.png)

The data was divided into three sets (train, dev and test) in an 80-10-10 ratio. We had to define an explicit dev set as cross validation approach on the train set wouldn’t be viable while using the undersampling and oversampling techniques as the train set in those cases wouldn’t exactly represent the real world case.

The evaluation metric used for determining the performance of the models was F1 score. Accuracy, although very intuitive, couldn’t be employed owing the to the imbalance in the dataset.

## Results
The following models were evaluated for performance on each of the three sampling techniques.

    1. Logistic Regression
    2. Support Vector Machines
    3. K Nearest Neighbours
    4. Decision Tree
    5. Random Forest
    6. Gradient Boosting
    7. XGBoost Classifier
    8. XG Boost Random Forest Classifier

The performance of the different models are summarised below.

**Original Dataset**

![Original](https://github.com/muhammedsalihk/Churn-Predictor-for-Telecom-Customers/blob/master/Images/Original.png)

**Undersampling**

![Undersampling](https://github.com/muhammedsalihk/Churn-Predictor-for-Telecom-Customers/blob/master/Images/Under.png)

**Oversampling with SMOTE**

![Oversampling](https://github.com/muhammedsalihk/Churn-Predictor-for-Telecom-Customers/blob/master/Images/Over.png)

It can be seen that out of the models and sampling techniques we have tried, the best performance on the test set is obtained for Gradient Boosting with the oversampling technique. But from the results, it is clear that we are facing a high variance (overfitting) problem, especially in the oversampled dataset which means that there is further scope of improvement by tuning the hyperparameters further.
