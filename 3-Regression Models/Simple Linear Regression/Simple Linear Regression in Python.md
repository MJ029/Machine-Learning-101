# Simple Linear Regression in Python:

### 1 - Prerequisites:    
  - Basics of Numpy    
  - Basics of Pandas    
  - Basics of sklearn.linear_model.LinearRegression    
  - Basics of statsmodels.api.OLS    
  - Basics of matplotlib.pyplot

### 2 - Import Libraries:
- If you want to write your own program to predict Simple Linear Regression you need to import the needed libraries first. for most of the models in the course we are going to use sklearn libraries.
```py
#Imprort Libraries
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
from sklearn.linear_model import LinearRegression
from sklearn.metrics import r2_score
import statsmodels.api as sm
```

### 3 - Import Data-set:
- Importing our data-set is the next step, once we imported our data-set we need to identify Independent Variable(IV) and Dependent Variable(DV) out of data-set.
- Here we are using **Pandas** library to Import our data-set from the directory, it is recommended to keep the data-set in same directory where the python file is saved.
- We are specifying required No.of rows and columns using pandas.iloc method.
- Here in **[:, :-1]**, **:** refers to fetch all rows from our data-set and **:-1** refers to fetch all columns other than last column, since we have only one column as IV in our data-set will fetch only one ndArray as **X**
- **pandas.iloc.values** will actually fetch and load values from data-set to variable **X and y**.
```py
#Import Dataset
dataset = pd.read_csv('BillTip.csv')
X = dataset.iloc[:, :-1].values
y = dataset.iloc[:, 1].values
```

### 4 - Split Data into Training set and Test Set:
- Once we got our IV and DV, it is recommended to Split your data in to Training set and Test Set.
- But in our case our ID and DV contains only 6 rows we are not doing this step as of now for this Example, But please find the Below code to split your IV and DV.
```py
#Spliting to train/test sets
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
```

### 5 - Fit & Predict Model:
- Once our data set is spitted as **X and y** we can start our model fitting.
- to Fit our model we are going to use **LinearRegression** from **sklearn.linear_model**
- **Please refer the Documentation page to see the List of parameters it will accept.**
```py
# Fitting Simple Linear Regression to the Training set
regressor = LinearRegression()
regressor.fit(X_train, y_trian)
```

- once we created our LinearRegression model we need to fit it using .fit Method, that's it the fit method will do everything for you, simply we can call predict method to find predicted values
```py
#Predicting the Ourput
y_pred = regressor.predict(X_train)
```

### 6 - Find Intercept and Slope of our Prediction:
- The Fit method from LinearRegression will complete the problem for us, but we need to see the slope and intercept value. it is optional to check the predicted results
```py
# To find Vlaue of Intercept b0
print("Intercept --> ", round(regressor.intercept_, 3))

# to find value of Slope b1
print("Slope --> ", round(regressor.coef_[0], 3))
```

### 7 - Find SSR, SSE and SST:
- We have to manually check the SSR, SSE and SST values to cross verify the model prediction.
```py
# Get SSR
def getSSR(y_actual, y_pred):
    return round(sum(np.array([(i-(sum(y_actual)/len(y_actual)))**2 for i in y_pred])), 3)

SSR = getSSR(y_train, y_pred)
print("SSR --> ", SSR)

#Get SSE
SSE = round(regressor._residues, 3)
print("SSE --> ", SSE)

#Find SST
def getSST(SSE, SSR):
    return round(SSE + SSR, 3)

SST =getSST(SSE, SSR)
print("SST --> ", SST)
```

### 8 - Find Predicted R2 and Calculated R2:
```py
#Calculate r2
r2 = round(SSR/SST, 3)*100
print("R2 Calculated --> ", r2)

# To find Accuracy r2
print("R2 Model Predicted", round(r2_score(y_train, y_pred), 3) * 100)
```

### 9 - Plot your Results:
- Plot and Visualize your results using Matplotlib.plot
```py
# Visualising the results
plt.scatter(X_train, y_train, color = 'red')
plt.plot(X_train, y_pred, color = 'blue')
plt.title('Bill (vs) Tip Amount')
plt.xlabel('Bill Amount')
plt.ylabel('Tip Amount')
plt.show()
```

- The above code will give you the following Result

<p align="center">
  	<img width="419" height="296" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/References/BillvsTip.JPG?raw=true">
</p>

### 10 - Print Summary:
- There is no function available in SkLearn to print report summary like stats model library, so we need to run our model in statsmodel.OLS to print summary
```py
# Get summary from Status Model, This is optional part to ensure our prediction summary from stats model
X_stats = sm.add_constant(X) # adding a constant
model = sm.OLS(y, X_stats).fit()
predictions = model.predict(X_stats)
print(model.summary())
```


- The above code will give us the following Summary as Output

<p align="center">
  	<img width="562" height="347" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/References/BillvsTipSummary.JPG?raw=true">
</p>
