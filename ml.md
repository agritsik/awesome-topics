### Supervised VS. Unsupervised [\*](https://leetcode.com/explore/featured/card/machine-learning-101/287/what_is_ml/1620/)
Given a machine learning problem, first of all, one can determine whether it is a supervised or unsupervised problem.
- In a **supervised learning task**, the data sample would contain a target attribute {y}y, also known as *ground truth*.
- In contrary to the *supervised learning task*, we do not have the *ground truth* in an **unsupervised learning task**.

### Big 3" machine learning tasks [\*](https://elitedatascience.com/machine-learning-algorithms)
- **Regression** (e.g. Linear Regression, Regression Tree, Deep Learning) is the **supervised** learning task for modeling and predicting continuous, numeric variables. 
*Examples* include predicting real-estate prices, stock price movements, or student test scores.
- **Classification** (e.g. Logistic Regression, Classification Tree, Deep Learning) is the **supervised** learning task for modeling and predicting categorical variables. 
*Examples* include predicting employee churn, email spam, financial fraud, or student letter grades.
- **Clustering** is an **unsupervised** learning task for finding natural groupings of observations (i.e. clusters) based on the inherent structure within your dataset. 
*Examples* include customer segmentation, grouping similar items in e-commerce, and social network analysis.

### Machine Learning Workflow [\*](https://leetcode.com/explore/featured/card/machine-learning-101/281/how_to_ml/1624/)

1. **Determine on which type of machine learning problems we would like to solve**, i.e. *supervised* vs. *unsupervised*. We say that the *data is labeled*, if one of the attributes in the data is the desired one, i.e. the target attribute.
2. For the *supervised* machine learning algorithms, we further **determine the type of the generated model**: *classification* or *regression*, based on the expected output of model, i.e. *discrete value for classification model* and *continuous value for regression model*.
1. Once we determine on the type of model that we would like to build out of the data, we then go ahead to **perform the feature engineering**, which is a group of activities that tranform the data into the desired format.


### Underfitting VS. Overfitting
- **An underfitting model** is the one which does not fit well with the training data, i.e. significantly deviated from the ground truth. One of the causes of underfitting could be that the model is over-simplified for the data, therefore it is not capable to capture the hidden relationship within the data.
- **An overfitting model** is the one which fits well with the training data, i.e. little or no error, however does not generalized well to the unseen data. Contrary to the case of underfittng, a over-complicated model that is able to fit every bit of the data, would fall into the traps of noises and errors.
<img src="https://github.com/agritsik/awesome-topics/blob/master/ml1.png" height="150px">
