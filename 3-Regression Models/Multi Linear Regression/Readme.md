# Multi-Linear Regression

**Note:** Please remember the below list of words in your mind before getting into the course   
	1. IV = Independent Variable (or) Predictor variable   
	2. DV = Dependent Variable (or) Response variable   
	3. SLR = Simple Linear Regression   
	4. MLR = Multi-Linear Regression (or) Multiple Linear Regression   
	5. P_Value -> [Ref_URL_1](https://www.mathbootcamps.com/what-is-a-p-value/) and [Ref_URL_2](https://www.wikihow.com/Calculate-P-Value) 

### 1. Introduction
- Hello, Welcome to second part of Regression Models. I hope you might have an clear understanding of SLR and how to implement it in python. Lets move on to the next topic in Regression models. Today we are going to discuss about Multi-Linear Regression(MLR).
- We move from the SLR model with one predictor(Independent Variable) to the multiple linear regression model with two or more predictors(Independent Variable's).
  
<p align="center">
  <img width="350" height="40" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Multi%20Linear%20Regression/References/MLR-Equation.JPG">
</p>    

- One good news here is that everything you learned about the SLR extends with minor modification in MLR. The key difference's between SLR and MLR are listed below
	- **Relationship:** SLR follows ***One-to-One*** Relationship between IV to DV, where-else MLR follows ***Many-to-One*** Relationship between IV's to DV.

<p align="center">
  <img width="901" height="468" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Multi%20Linear%20Regression/References/SLR-MLR-Diff.JPG">
</p>    

- Lets see the concept of MLR using the following example [[Dataset.csv]](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Multi%20Linear%20Regression/Datasets/Logistics.csv). In the dataset we have 4 IV's {Miles Traveled(<b>X<sub>1</sub></b>), NoOfDeliveries(<b>X<sub>2</sub></b>) and GasPrice(<b>X<sub>3</sub></b>) and City[Base Location of truck] (<b>X<sub>4</sub></b>)} and one DV {TravelTime(<b>Y</b>)}. Before jumping to use-case i would like to give you heads up on the below 2 topics
	- [Dummy Variables](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/3-Regression%20Models/Multi%20Linear%20Regression#2-dummy-variables)
	- [Model selection for MLR](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/3-Regression%20Models/Multi%20Linear%20Regression#3-model-selection-for-mlr)

### 2 Dummy Variables:   
- Lets assume that one of our independent variable has a [categorical data](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/2-Data%20Pre-Processing#2-handling-categorical-data). 
- We all know that Most of the Machine Learning models plays with Numerical data, categorical data plays a major role when it comes to model processing it is one of the useful feature for our model. So we need to encode this categorical data to binary format, but when encoding categorical data to binary format there is a chance our model will fall due to a well known problem called ***Dummy variable trap***. We need to address this issue in data-preprocessing phase.

#### 2.1 What is Dummy variable:   
- Basically encoding categorical Variable to binary form are known as Dummy variable.
- Suppose you have state column in your data-set with 3 state values as follows "**California**, **New-York** and **los angeles**" we need to encode this values to proper numerical value before processing our model.
- If you see the below image will show you how label encoder encoded categorical data into numerical data.

<p align="center">
  <img width="801" height="275" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Multi%20Linear%20Regression/References/S1.JPG?raw=true">
</p>   

- When you encode the categorical columns it will create one column for each unique value in Categorical column, ie: Unique(NoOfValues) = NoOfNewColumns   
- The below image shows how OneHotEncoder encodes categorical data into binary form. If you see the below image you can clearly identify among 3 encoded columns without having any one of the encoded column we can derive our model.
<p align="center">
  <img width="838" height="286" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Multi%20Linear%20Regression/References/S2.JPG?raw=true">
</p>       

- Basically the encoded values are in binary form so always we need to keep n-1 variables after the encoding, (n=> count distinct of value in categorical  column). 
- Ex:   
	2 categories means 1    
	5 categories means 4   
	3 categories means 2 and so on.
- Lets see the first row form the below image, here we removed the first column from our data set to avoid dummy variable trap, still the model make sense.

<p align="center">
  <img width="893" height="279" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Multi%20Linear%20Regression/References/S3.JPG?raw=true">
</p>   


#### 2.2 What is Dummy variable trap:
- For Example: when we are encoding categorical column with 3 values one column will become "Dummy", which means we are duplicating the column by keeping it in our Equation.
- And you should always remember **D2 = 1 - D1**, where in case of Dummy Variable.
- If we keep the dummy variable in our equation will basically lead us to Multi-collinearity problem.
- And we cannot keep the constant and 3 dummy variable in our Equation.   
**Note:** 
	D2 = Dummy variable 2   
	D1 = Dummy variable 1


### 3 Model selection for MLR:
- When it comes to SLR, the process it pretty simple but in case of MLR we need to consider anyone of the following method before building our model. this help us to identify the best predictors for our model instead keeping all the IV's and making our model too robust.
#### 3.1 All - in:  
- Basically keeping all Independent Variables to build our model, we can proceed with this approach when we have the following.
	1. By having prior knowledge of the model and data-set.
	2. By the case you have to because of your Framework requirement.
	3. Preparing for Backward elimination.   

#### 3.2 Backward Elimination: (Fastest one of all of them and recommended to choose this model)

<p align="center">
  <img width="800" height="500" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Multi%20Linear%20Regression/References/BWE.jpg?raw=true">
</p>   

#### 3.3 Forward Selection:

<p align="center">
  <img width="800" height="540" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Multi%20Linear%20Regression/References/FWE.jpg?raw=true">
</p>   

#### 3.4 Bidirectional Elimination: (Most iterative process)

<p align="center">
  <img width="800" height="560" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Multi%20Linear%20Regression/References/BDE.jpg?raw=true">
</p>   

#### 3.5 Score Comparison: (Most resource Consuming model)

<p align="center">
  <img width="761" height="368" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Multi%20Linear%20Regression/References/SC.JPG?raw=true">
</p>   

- Once you have picked the right methods to derive our model we can start building our model in the same wat that we have done for SLR.
- Among all models ***Backward Elimination*** is the most commounly used model for MLR.
- Our usecase showed below in step-by-step python also uses same method to build the model.

### 4. Multi-Linear Regression in Python:
- [How to Write your first program](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Multi%20Linear%20Regression/Multi-Linear%20Regression%20in%20Python.md#multi-linear-regression-in-python)
- If you completed the above step, Congrats you have created your second machine learning model [MLR] using Python.


### 5. Additional Use-cases:
1. Create a Machine Learning model in python to solve Multivariate Problem.[[Logistic.csv]](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Multi%20Linear%20Regression/Datasets/Logistics.csv)
2. Create a Machine Learning model in python to solve Multivariate Problem.[[Car Mileage.csv]](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Multi%20Linear%20Regression/Datasets/carMPG.csv)
3. Create a Machine Learning model in python to solve Multivariate Problem.[[IQlevel.csv]](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Multi%20Linear%20Regression/Datasets/IQLevel.csv)


##### Reference URL:
[To Understand Concepts Behind MLR - Video](https://www.youtube.com/watch?v=dQNpSa-bq4M&list=PLIeGtxpvyG-IqjoU8IiF0Yu1WtxNq_4z-)    
[Use-case Solutions and References](https://github.com/ManikandanJeyabal/Workplace/tree/master/DataScience/Regression/Multi%20Linear%20Regression)

##### See Also
- [Simple Linear Regression](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/3-Regression%20Models/Simple%20Linear%20Regression#simple-linear-regression)
- [Polynomial Regression](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/3-Regression%20Models/Polynomial%20Regression#polynomial-regression)
- [SVR - Support Vector Regression](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/3-Regression%20Models/Support%20Vector%20Machine/ReadMe.md#svr---support-vector-regression)
- [Decision Tree Regression](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/3-Regression%20Models/Decision%20Trees#decision-tree-regression)
- [Random Forest Regression](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/3-Regression%20Models/Random%20Forest%20Regression#random-forest-regression)
