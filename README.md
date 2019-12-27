# UCI Heart Disease Classification

In this project, we aim to train a classifier to accurately classify a person whether or not has a heart disease problem. In particular, we would like to compare several classification algorithms: logistic regression, random forests, support vector machine and k-nearest neighbours based on sensitivity and classification accuracy. Also, it will be beneficial to see if we can reduce the number of features to perform a good classification that may potentially lower the costs of collecting expensive features in the future. Most people believe that age should be a strong indicator whether a person has a heart disease problem. Our project will also validate this claim and see if there are any better indicators with hypothesis testing.

## Questions of interests

What is the relationship between age and heart disease?

Will combining several predictors into one new predictor variable be useful to improve our model?

What will be the best combination of features we should use based on the classification algorithm?

Can we reduce the number of features and still get a satisfactory classification performance?

What is the best classification rate that we can come up with to predict the presence of heart disease?

## Data Exploration

We first explore the data by making use of boxplots, histograms, density plots, and a scatterplot matrix. In particular, we use boxplots to explore the distribution of some quantitative variables such as maximum heart rate achieved, serum cholesterol, age, resting blood pressure and by gender and disease to see if there is any significant differences among different genders and types of disease. 

Then, we would split the data set into training and testing datasets by having 80 percent of the data to be training and 20 percent of the data to be testing. We then implemented several algorithms including logistic regression, random forests, support vector machine, and K-nearest neighbors to classify the presence and absence of heart disease. We also conduct outlier detection to see if there is a performance gain by dropping some potential outliers in the data.

## Classification Model

### Logistic Regression

We first compare two logistic models that use all the predictor variables: model 1 and model 2. The difference between these two models is that we dropped two potential outliers (row 259 and 4) by looking at the standardized deviance residual plot and use the rest of the data to train the model 2 to see if there is a performance gain in comparison with model 1.

Next, we also train three logistic regression models with different numbers of predictors. Model 3 utilizes all first order term and two-way interaction term. Model 4 is only trained with quantitative predictor variables including age, resting blood pressure, serum cholesterol, maximum heart rate achieved, oldpeak, and major vessels. Model 5 will be trained by a reduced number of features based on our feature selection method. Then, we will select the model with the highest accuracy and sensitivity rate to compare with other algorithms.

#### Probability threshold selction for logistic regression classification

Besides, we use Receiver Operating Characteristics (ROC) curve to see what are some best cut-off threshold for getting the most accurate classification rate for each model by picking thresholds that maximizes the area under the curve as it measures how good our model is able to distinguish two classes of the response variable.

#### Features selection

We want to estimate the variable importance to see if we can reduce the number of features and still achieve a satisfactory result. The importance can be estimated using a ROC curve analysis conducted for each attribute.


## Evaluation Metric

Our evaluation metric is based on sensitivity and the accuracy rate. Since it is more important to
correctly identify people who have a heart disease, we set the presence of heart disease as positive. Sensitivity is the true positive rate, which is the percentage of people with heart disease who are correctly identified as having the condition.


## Conclusion

In conclusion, we see people who have heart disease are mostly around the age of 60. Also, the predictor variable, age, doesn’t explain the response variable of heart disease as good as the number of major vessels in our logistic regression model. Moreover, we see that combining features into one predictor variable by using two-way interaction terms does not necessarily improve classification performance in general. When we look at our logistic regression models, we see that reducing number of features for training can improve model performance by excluding the predictor named fasting blood sugar. We have found that the following predictors are particularly important in logistic regression model for classification: major vessels, chest pain type, thal, sex, resting blood pressure, slope, oldpeak, serum cholestoral, exercise induced angina and maximum heart rate achieved.

## Data Source

[UCI heart disease data set](http://archive.ics.uci.edu/ml/datasets/statlog+(heart))

## Author

Kenneth Lee ([@kenneth-lee-ch](https://github.com/kenneth-lee-ch))

## License

[MIT](https://choosealicense.com/licenses/mit/)

If you do find this script useful, a link back to this repository would be appreciated. Thanks!