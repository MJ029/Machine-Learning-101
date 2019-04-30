# Simple Linear Regression in Python:

### 1 - Prerequisites:    
  - Basics of Numpy    
  - Basics of Pandas    
  - Basics of sklearn.linear_model.LinearRegression    
  - Basics of statsmodels.api.OLS    
  - Basics of matplotlib.pyplot

### 2 - Import Libraries:
- If you want to write your own program to predict Simple Linear Regression you need to import the needed libraries first.

<p align="center">
  	<img width="556" height="119" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/References/python-1.JPG?raw=true">
</p>

### 3 - Import Data-set:
- Importing our data-set is the next step, once we imported our data-set we need to identify Independent Variable(IV) and Dependent Variable(DV) out of data-set.
- Here we are using **Pandas** library to Import our data-set from the directory, it is recommended to keep the data-set in same directory where the python file is saved.
- We are specifying required No.of rows and columns using pandas.iloc method.
- Here in **[:, :-1]**, **:** refers to fetch all rows from our data-set and **:-1** refers to fetch all columns other than last column, since we have only one column as IV in our data-set will fetch only one ndArray as **X**
- **pandas.iloc.values** will actually fetch and load values from data-set to variable **X and y**.

<p align="center">
  	<img width="554" height="73" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/References/python-2.JPG?raw=true">
</p>

### 4 - Split Data into Training set and Test Set:
- Once we got our IV and DV, it is recommended to Split your data in to Training set and Test Set.
- But in our case our ID and DV contains only 6 rows we are not doing this step as of now for this Example, But please find the Below code to split your IV and DV.

<p align="center">
  	<img width="677" height="60" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/References/python-10.JPG?raw=true">
</p>

### 5 - Fit & Predict Model:
- Once our data set is spitted as **X and y** we can start our model fitting.
- to Fit our model we are going to use **LinearRegression** from **sklearn.linear_model**
- **Please refer the Documentation page to see the List of parameters it will accept.**

<p align="center">
  	<img width="559" height="61" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/References/python-3.JPG?raw=true">
</p>

- once we created our LinearRegression model we need to fit it using .fit Method, that's it the fit method will do everything for you, simply we can call predict method to find predicted values

<p align="center">
  	<img width="555" height="50" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/References/python-4.JPG?raw=true">
</p>

### 6 - Find Intercept and Slope of our Prediction:
- The Fit method from LinearRegression will complete the problem for us, but we need to see the slope and intercept value. it is optional to check the predicted results

<p align="center">
  	<img width="557" height="92" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/References/python-5.JPG?raw=true">
</p>

### 7 - Find SSR, SSE and SST:
- We have to manually check the SSR, SSE and SST values to cross verify the model prediction.

<p align="center">
  	<img width="647" height="276" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/References/python-6.JPG?raw=true">
</p>

### 8 - Find Predicted R2 and Calculated R2:
<p align="center">
  	<img width="558" height="110" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/References/python-7.JPG?raw=true">
</p>

### 9 - Plot your Results:
- Plot and Visualize your results using Matplotlib.plot

<p align="center">
  	<img width="557" height="124" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/References/python-8.JPG?raw=true">
</p>

- The above code will give you the following Result

<p align="center">
  	<img width="419" height="296" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/References/BillvsTip.JPG?raw=true">
</p>

### 10 - Print Summary:
- There is no function available in SkLearn to print report summary like stats model library, so we need to run our model in statsmodel.OLS to print summary

<p align="center">
  	<img width="737" height="85" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/References/python-9.JPG?raw=true">
</p>


- The above code will give us the following Summary as Output

<p align="center">
  	<img width="562" height="347" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/References/BillvsTipSummary.JPG?raw=true">
</p>