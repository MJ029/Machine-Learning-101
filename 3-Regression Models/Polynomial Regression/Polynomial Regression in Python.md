# Polynomial Regression in Python

### 1 - Prerequisites:    
  - Basics of Numpy    
  - Basics of Pandas    
  - Basics of sklearn.linear_model.LinearRegression      
  - Basics of matplotlib.pyplot
  - Basics of sklearn.preprocessing (Imputer, PolynomialFeatures, StandardScaler)
  - Basics of sklearn.model_selection.train_test_split
  - Basics of sklearn.metrics

### 2 - Import Libraries:
- If you want to write your own program to predict Polynomial Regression you need to import the needed libraries first.
- The below libraries are used in this program demonstration.
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.preprocessing import Imputer, PolynomialFeatures, StandardScaler
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn import metrics
```

### 3 - Import Data-set:
- Importing our data-set is the next step, once we imported our data-set we need to identify Independent Variable(IV) and Dependent Variable(DV) out of data-set.
- Here we are using **Pandas** library to Import our data-set from the directory, it is recommended to keep the data-set in same directory where the python file is saved.
- Here from Pandas data-set we are directly creating our X(IV) and y(DV).
```py
dataset = pd.read_csv('carMPG.csv')
X = dataset[['Horsepower']]
y = dataset['MPG']
```

### 4 - Feature Scaling:(Optional)
- This step is optional, if you data-set having Dependent/Independent Variable dominating other then we have to perform feature scaling.
- We have already imported the StandardScaler class.
```py
sc_X = StandardScaler()
X = sc_X.fit_transform(X)
``` 
- Please [click here](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/2-Data%20Pre-Processing#4-feature-scaling) to know how to handle Feature Scaling in your problem.

### 5 - Creating Polynomial Feature Model
- The next step in Polynomial Regression is the create a Polynomial features of IV's. To do this we are going to use a library form ```sklearn``` called ```PolynomialFeatures```. which takes one important parameter called **degree**, this degree is similar to learning rate in NeuralNetworks, based on the degree value our model will try to best fit to the data-set. 
- By default Degree = 2.
```py
poly_reg= PolynomialFeatures(degree=4)
X_Poly = poly_reg.fit_transform(X)
poly_reg.fit(X_Poly, y)
```
- In the above coed you can see that we are creating the object of ```PolynomialFeatures``` with **degree=4**, here we are overriding the default value 2 to 4.
- We are creating a new matrix feature **X_poly** to hold the transformed matrix of X in to polynomial form.
- Again we are fitting our newly created **X_poly** with y(DV). we are doing this because we are trying to fit our model with polynomial feature matrix with degree of 4.

### 6 - Create Linear model with Polynomial feature's X_poly.
- Now we are going to create a Linear Model for out Polynomial Regressor. To proceed with this you need to do the following steps.
```py
py_reg = LinearRegression()
py_reg.fit(X_Poly, y)
```
- The above step is as same as creating a SLR, a small difference here is that we are passing X_poly instead our Matrix (X).
- Now our PNR model is ready to predict data, lets visualize the result in graph.


### 7 - Visualize the result-set using matplotlib.pyplot.
- use the following code to visualize the result.
```py
plt.scatter(X, y, c='red')
plt.plot(X, py_reg.predict(poly_reg.fit_transform(X)), color = 'blue')
plt.title('MPG based on Acceleration')
plt.xlabel('Acceleration')
plt.ylabel('MPG')
plt.show()
```

### 8 - Determine Co-eff, Intercept and Model Accuracy:
- use the following code to determine Model predictions Co-eff, Intercept and Accuracy with MSR.
```py
print('Co-Eff: --> ', py_reg.coef_) 
print('Intercept: --> ', py_reg.intercept_)

print("RSME --> ", np.sqrt(metrics.mean_squared_error(y,py_reg.predict(poly_reg.fit_transform(X)))))
print('Score on Training model--> ', py_reg.score(X_Poly, y))
```
