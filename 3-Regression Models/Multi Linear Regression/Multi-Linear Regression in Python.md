# Multi Linear Regression in Python:

### 1 - Prerequisites:    
  - Basics of Numpy    
  - Basics of Pandas    
  - Basics of sklearn.linear_model.LinearRegression    
  - Basics of statsmodels.api.OLS    
  - Basics of sklearn.preprocessing.LabelEncoder and sklearn.preprocessing.LabelEncoder

### 2. Import Libraries:
- As part of MRL model creation you need to import the below libraries.
```py
import pandas
import numpy
from sklearn import model_selection, preprocessing, linear_model
import statsmodels.api as sm
```

### 3. Import Data-set:
- The next step to be import out data-set in to model, it is recommended to keep your .py file and your data-set in same folder as best practice.
- To import data-set into out model use the below code.
- Once we imported our data-set we need to identify Independent Variable's(IV) and Dependent Variable(DV) out of data-set. as of now we are going to follow general way(Not MLR's Model selection process).
- Here we are using Pandas library to Import our data-set from the directory, it is recommended to keep the data-set in same directory where the python file is saved.
- We are specifying required No.of rows and columns using pandas.iloc method.
- Here in [:, :-1], : refers to fetch all rows from our data-set and :-1 refers to fetch all columns other than last column, since we have only one column as IV in our data-set will fetch only one ndArray as X
- pandas.iloc.values will actually fetch and load values from data-set to variable X and y.
```py
dataset = pandas.read_csv('Logistics.csv')
X = dataset.iloc[:, :-1].values
y = dataset.iloc[:, -1].values
```

### 4. Handling Categorical Data and Dummy Variable Trap:(Optional)
- This step is optional step, if your data-set has categorical data the you can proceed with this step. and keep in mind this is completely and optional step.
- To Encode Categorical data as we discussed before we are going to use the following 2 libraries.
- In our example we are having categorical data in 4'th[3'rd index in Array] column, so we are considering array index 3 for categorical data encoding.
```py
lable_encoder = preprocessing.LabelEncoder()
X[:, 3] = lable_encoder.fit_transform(X[:, 3])
onehot_encoder = preprocessing.OneHotEncoder(categorical_features = [3])
X = onehot_encoder.fit_transform(X).toarray()
X = X[:, 1:]
```
- Please [click here](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/3-Regression%20Models/Multi%20Linear%20Regression#2-dummy-variables) to find how categorical data works.

### 5. Feature Scaling:(Optional)
- This step is also optional, if you data-set having Dependent/Independent Variable dominating other then we have to perform feature scaling.   
```py
from sklearn.preprocessing import StandardScaler 
sc_X = StandardScaler()
X = sc_X.fit_transform(X)
``` 
- Please [click here](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/2-Data%20Pre-Processing#4-feature-scaling) to know how to handle Feature Scaling in your problem.

### 6. Model Selection using Backward Elimination:
- Usually for all our model creation and evaluation we will stick with sklearn library, but for this model selection alone we are going to proceed with statlmodel library. [Click here](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/Python%20%2B%20Machine%20Learning%20%2B%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/3-Regression%20Models/Multi%20Linear%20Regression#32-backward-elimination-fastest-one-of-all-of-them-and-recommended-to-choose-this-model) to see the Backward Elimination work flow.
- In sklearan everything is auto initialized like constants intercept etc... but in statsmodel An intercept is not included by default and should be added by the user.
```py
X_stats = sm.add_constant(X)
X_opt = X_stats[:, [0, 1, 2, 3, 4, 5]]
reg = sm.OLS(y, X_opt).fit()
reg.summary()
```
- The above code will produce the following result. 

<p align="center">
  <img width="652" height="527" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/3-Regression%20Models/Multi%20Linear%20Regression/References/OLS_1.JPG?raw=true">
</p>   

- If you remembered the Backward Elimination process the process it identify the predictor having higher than significant value in our case (SL=0.005) and remove it and fit model with remaining predictors and repeat the same until P > SL condition fails.
- So here in our model (<b>X<sub>1</sub></b>) - [One of Encoded Categorical variable] is having higher P-Value = 0.964. so remove this and fit model with remaining predictors.
- In the second iteration we ran the following code.
```py
X_opt = X_stats[:, [0, 2, 3, 4, 5]]
reg = sm.OLS(y, X_opt).fit()
reg.summary()
```
- By running the above code we got the below result as summary. 

<p align="center">
  <img width="653" height="519" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/3-Regression%20Models/Multi%20Linear%20Regression/References/OLS_2.JPG?raw=true">
</p>   

- In the summary it clearly shows the current (<b>X<sub>1</sub></b>) - [second encoded categorical variable] is having higher P-Value = 0.864. so remove this and fit model with remaining predictors.
- If you noticed a difference between the above 2 summaries you can clearly see the P-Value for remaining Predictors decreasing by removing the unwanted Predictors. this effect of one Independent variable with another independent variable is known as **Multi-collinearity** problem.
- Okay, lets remove the predictor and proceed with next iteration
```py
X_opt = X_stats[:, [0, 3, 4, 5]]
reg = sm.OLS(y, X_opt).fit()
reg.summary()
```
- The above code will produce below summary.

<p align="center">
  <img width="658" height="485" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/3-Regression%20Models/Multi%20Linear%20Regression/References/OLS_3.JPG?raw=true">
</p>   

- In the summary it clearly shows the current (<b>X<sub>1</sub></b>) - [Miles Traveled] is having higher P-Value = 0.527. so remove this and fit model with remaining predictors.
- Further if you notice all the above summaries the Difference between R-Squared and Adj R-Squared is getting reduced.
- Okay, lets remove the predictor and proceed with next iteration.
```py
X_opt = X_stats[:, [0, 4, 5]]
reg = sm.OLS(y, X_opt).fit()
reg.summary()
```
- The above code will produce below summary.

<p align="center">
  <img width="655" height="442" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/3-Regression%20Models/Multi%20Linear%20Regression/References/OLS_4.JPG?raw=true">
</p>   

- In the summary it clearly shows the current (<b>X<sub>2</sub></b>) - [GasPrice] is having higher P-Value = 0.148. which is quit higher than our SL=0.005 so remove this and fit model with remaining predictors.
```py
X_opt = X_stats[:, [0, 4]]
reg = sm.OLS(y, X_opt).fit()
reg.summary()
```

<p align="center">
  <img width="670" height="423" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/3-Regression%20Models/Multi%20Linear%20Regression/References/OLS_5.JPG?raw=true">
</p>   

- Bravo the current model satisfy our condition and it gives P-Value < SL. so our model is ready and we can go ahead to next step.
- Note: for your understanding i have demonstrated the example in step-by-step way, you have to find a way to automate the above completed step and proceed with model building.

### 7. Splitting the data-set into the Training set and Test set:
- Once you identified the Predictors for your model you can proceed the remaining steps like SLR.
- So the next step will be splitting our model into Train/Test sets.
- For this task we are going to use a module called train_test_split from sklearn.model_selection.(Note: in old version of sklearn the train_test_split was under cross_validation model)
```py
X_train, X_test, y_train, y_test = model_selection.train_test_split(X, y, test_size = 0.2, random_state = 0)
```
- The above code will split your data-set into Training and Test sets. if you want to know more about Train/Test split please [click here](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/2-Data%20Pre-Processing#3-spiting-your-data-set-into-devtrainingtest-set)


### 8. Model Creation using sklearn.linear_model library:
- use the following code to create and fit your model with Linear Regressor using sklearn.linear_model
```py
regressor = linear_model.LinearRegression()
regressor.fit(X_train, y_train)
```

### 9. Predict the Model output:
- Once your model is ready and fitted, the next step is to predict the model output and validate it.
- use the below code to predict your model output
```py
y_pred = regressor.predict(X_test)
```

### Determine Co-eff, Intercept and R-Squared(Model Accuracy) values:
- Use the below code to determine your model metrics like Co-eff, Intercept and Accuracy of your model.
```py
print('Co-Eff: --> ', regressor.coef_) # Here we have 3 Co-eff since we have 3 indipendent variable
print('Intercept: --> ', regressor.intercept_) # Intercept will be same as SLR we have only one Intercept.
print('Score on Training model--> ', regressor.score(X_train, y_train))
```
