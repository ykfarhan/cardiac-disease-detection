# Module 3 Final Project: Detecting Cardiovascular Disease
Yasir Karim

Source: Kaggle
## Introdcution
We were tasked with completing a machine learning project involving classification models. The approach to the given task was driven by data sets rather than an initial question. A suitable data set had to be found before we could settle on a question to answer. The final data set was picked based on having a binary target variable with substantial number of features and observations. The cardiovascular disease dataset was retrieved from kaggle. It has information on patients at the time of checking into a medical facility, specifically, readings on their blood pressure, height, and weight among others. and the  Unfortunately, the original data source could not be traced. Therefore, assumptions had to be made about the location, demographic and subjective answers. However, after parsing through similar data sets, we can predict that this data was collected from participating hospitals around the United States. The target columns contains information on the patients heart condition, specifically, if they had any sort of cardiac disease that was detected later.
## Data Cleaning & Exploration
Our mission is to successfully predict heart conditions of incoming patients and determine which factors contribute to this aspect the most. We had to do further research on medical metrics such as blood pressure, glucose and cholesterol levels. In order to clean the data and engineer new features, we needed to know the normal levels of these metrics and how they are classified. There are subjective features such as patients answering questions about their smoking and alochol habits, we had to be careful about how we use these columns as they run the risk of being unreliable. In terms of class balance, the data set was almost perfectly balanced among the two classes.

For our initial exploration of the original data set and cleaning it in order to create a train-test split:

`see: data_cleaning_cardiac.ipynb`

For our feature engineering, visualization and modelling process:

`see: modelling_process_cardiac.ipynb`

For the final prediction on the holdout test set:

`see: Predicting_holdout_cardiac.ipynb`

## Queries:

We wanted to answer the following questions through our analysis and modelling of the data:

```
1. How accurately can we predict the presence of a cardiac disease in patients with the initial measurements?
2. Are there factors that contribute significantly to having a heart condition?
3. Which of these factors are the most significant compared to others?
4. Can we narrow down the number of information/measurements needed from patients to guess their heart condition in order to help them in advance?
```

## Modelling
After cleaning our original data set, we were left with 90% of the observations. Then, we split this data into two parts: the train data and test data. We used our train data to fit different classification models. Our target to get the best possible recall score and to be able to interpret the importance of the features. We used recall score because we wanted to minimize the number patients with a heart condition that we fail to predict. We used grid search in conjunction with all our models. The results are the following:

```
1. Decision Tree: 0.70
2. Random Forest: 0.70
3. K-Nearest Neighbors: 0.70
4. Logistic Regression: 0.63
5. Voting Classifier: 0.70
```
We decided to use refit the decision tree model to our entire train set because of its high recall score and the benefit of being highly interpretable. Using this model on the test set we achieved a recall score of

## Visualizations


## Conclusions

### Reccomendations

### Future Work



