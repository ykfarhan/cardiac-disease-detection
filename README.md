# Module 3 Final Project: Detecting Cardiovascular Disease
Yasir Karim

Source: Kaggle
## Introdcution
We were tasked with completing a machine learning project involving classification models. The approach to the given task was driven by data sets rather than an initial question. A suitable data set had to be found before we could settle on a question to answer. The final data set was picked based on having a binary target variable with substantial number of features and observations. The cardiovascular disease dataset was retrieved from kaggle. It has information on patients at the time of checking into a medical facility, specifically, readings on their blood pressure, height, and weight among others. and the  Unfortunately, the original data source could not be traced. Therefore, assumptions had to be made about the location, demographic and subjective answers. However, after parsing through similar data sets, we can predict that this data was collected from participating hospitals around the United States. The target columns contains information on the patients heart condition, specifically, if they had any sort of cardiac disease that was detected later.
## Data Cleaning & Exploration
Our mission is to successfully predict heart conditions of incoming patients and determine which factors contribute to this aspect the most. We had to do further research on medical metrics such as blood pressure, glucose and cholesterol levels. In order to clean the data and engineer new features, we needed to know the normal levels of these metrics and how they are classified. There are subjective features such as patients answering questions about their smoking and alochol habits, we had to be careful about how we use these columns as they run the risk of being unreliable. In terms of class balance, the data set was almost perfectly balanced among the two classes.

For our initial exploration of the original data set and cleaning it in order to create a train-test split:

`see:` [data_cleaning_cardiac.ipynb](https://github.com/ykfarhan/cardiac-disease-detection/blob/master/data_cleaning_cardiac.ipynb)

For our feature engineering, visualization and modelling process:

`see:` [modelling_process_cardiac.ipynb](https://github.com/ykfarhan/cardiac-disease-detection/blob/master/modelling_process_cardio.ipynb)

For the final prediction on the holdout test set:

`see:` [Predicting_holdout_cardiac.ipynb](https://github.com/ykfarhan/cardiac-disease-detection/blob/master/Predicting_holdout_cardiac.ipynb)

For the non-technical executive presentation:

`see:` [Presentantion.pdf](https://github.com/ykfarhan/cardiac-disease-detection/blob/master/presentation_cardiac_disease.pdf)

## Queries:

We wanted to answer the following questions through our analysis and modelling of the data:

```
1. How accurately can we predict the presence of a cardiac disease in patients with the initial measurements?
2. Are there factors that contribute significantly to having a heart condition?
3. Which of these factors are the most significant compared to others?
4. Can we narrow down the number of information/measurements needed from patients to guess their heart condition in order to help them in advance?
```

## Modelling
After cleaning our original data set, we were left with 90% of the observations. Then, we split this data into two parts: the train data and test data. We used our train data to fit different classification models. Our target to get the best possible recall score and to be able to interpret the importance of the features. We used recall score because we wanted to minimize the number patients with a heart condition that we fail to predict. We used grid search in conjunction with all our models to optimize the hyperparameters. The results are the following:

```
1. Decision Tree: 0.715
2. Random Forest: 0.716
3. K-Nearest Neighbors: 0.677
4. Logistic Regression: 0.621
5. Voting Classifier: 0.710
```
We decided to refit the decision tree model to our entire train set because of its high recall score and the benefit of being highly interpretable. Using this model on the test set we achieved a recall score of `0.699`. However, if we lowered our classification threshold from 0.5 to 0.36, our recall score jumps to almost ~ `0.84`. In terms of feature importance, Blood Pressure levels, Age and BMI were the most significant. 

## Visualizations

 We made visualizations during our exploratory data analysis process and after our modelling process.
 
 For visualizations during the E.D.A process:
 
 `see:` [Class Balance](https://github.com/ykfarhan/cardiac-disease-detection/blob/master/visualizations/class_balance.png)
 
 [Distrubution among some of the features](https://github.com/ykfarhan/cardiac-disease-detection/blob/master/visualizations/distplot.png)
 
 [Feature histrograms by class](https://github.com/ykfarhan/cardiac-disease-detection/blob/master/visualizations/histograms_by_class.png)
 
 For feature importance levels among different models:
 
 `see:` [Feature importance of decision tree](https://github.com/ykfarhan/cardiac-disease-detection/blob/master/visualizations/feature_imp_dct.png)
 
 [Logistic regression feature coefficients](https://github.com/ykfarhan/cardiac-disease-detection/blob/master/visualizations/feat_coef_logreg.png)
 
 For anaylisis after modelling and prediction:
 
 `see:` [Proportion with disease vs no-disease by groups](https://github.com/ykfarhan/cardiac-disease-detection/blob/master/visualizations/proportions_by_groups.png)

[Proportion with disease among different age groups](https://github.com/ykfarhan/cardiac-disease-detection/blob/master/visualizations/disease_by_age.png)

## Conclusions

### Reccomendations
* Use the predictive model in identifying patients with cardiac disease.
* When a patient is checking in, measure the important features to identify cardiac disease.
* Suggest non-emergency patients to take further tests to successfully identify heart condition.
* Provide the emergency patients with appropriate healthcare.

### Future Work
* Find the original data source in order to reduce assumptions made and correctly identify background and context.
* Use bagging and boosting methods to try and increase recall score.
* Find similar data sets that have a lot more features to work with.
* Consult with a healthcare expert to in order to gain more knowledge about the ins and outs of medical facility.




