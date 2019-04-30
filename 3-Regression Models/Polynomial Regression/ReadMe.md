# Polynomial Regression

##### Notes: 
- Please remember the below list of words in your mind before getting into the Session.
	1. IV = Independent Variable (or) Predictor variable
	2. DV = Dependent Variable (or) Response variable
	3. PNR = Polynomial Regression
	4. SLR = Simple Linear Regression

### 1. Introduction
- Welcome to the 3'rd module of Regression, Polynomial Regression. In this session you will learn how to build a machine learning model using polynomial Regression for data-set quadratic in nature.
- Polynomial Regression model is the one of the regression model which  is still considered to be linear model as the coefficients/weights associated with the features are still linear. However the curve that we are fitting is quadratic in nature.
- Suppose if the Higher order Equation for SLR is as below

<p align="center">
  <b>y&#770;<sub>i</sub> = <i>b</i><sub>0</sub> + <i>b</i><sub>1</sub><i>x</i></b>
</p>    

- Then the Higher order equation for Polynomial Regression will be as below

<p align="center">
  <img width="250" height="40" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Polynomial%20Regression/Reference/Regression%20Model.JPG?raw=true">
</p>    

- Lets take an example and proceed with business problem. we have a [[dataset.csv]](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Polynomial%20Regression/Dataset/carMPG.csv), which contains 2 columns {{Acceleration(<b>X<sub>1</sub></b>) and MPG(<b>Y</b>)} here our IV is **Acceleration** and DV is **MPG**. we are going to identify trend between IV and DV using Polynomial Regression.
- Before Proceeding with **PNR**, lets solve the same problem using **SLR** and below results shows the summary of SLR.  
- **Best Fit Line: SLR**

<p align="center">
  <img width="416" height="294" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Polynomial%20Regression/Reference/SLR_BFLine.JPG?raw=true">
</p>    

- **Model Co-eff, Intercept and Accuracy:**

<p align="center">
  <img width="329" height="70" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Polynomial%20Regression/Reference/SLR_Accuracy.JPG?raw=true">
</p>  

- In the above plot you can clearly see the best fit line is a straight line not meeting our polynomial feature, so for this case we need to consider Polynomial Regression and for this we are going to use a module from sklearn called ```sklearn.preprocessing.PolynomialFeatures```. This model is best suit for data-set nature in quadratic form and will get the best-fit line as below.
- **Best Fit Line: PNR**

<p align="center">
  <img width="404" height="296" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Polynomial%20Regression/Reference/PNR_BFLine.JPG?raw=true">
</p>    

- **Model Co-eff, Intercept and Accuracy:**

<p align="center">
  <img width="534" height="74" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Polynomial%20Regression/Reference/PNR_Accuracy.JPG?raw=true">
</p>  

- If you want to improve your model accuracy, you need to think of an important topic called Bias-Variance problem and trade-off between Bias and Variance. since we are trying to adjust the Degree of PNR (which intend tell us how our models is learning for each degree)its very important to discuss about Bias-variance trade-off.  
### 2. Bias-Variance trade-off:
- **Bias** refers to the error due to the model’s simplistic assumptions in fitting the data.
- A **high bias** means that the model is unable to capture the patterns in the data and this results **under-fitting**.
- **Variance** refers to the error due to the complex model trying to fit the data.
- A **high variance** means the model passes through most of the data points and it results **over-fitting**.
- we can categorize Bias-Variance problem into the below 4 categories
	1. <b>High Bias & Low Variance:</b> which shows your model has Low accuracy(performs very poor) and low variance in nature to predict unknown variable, or it may happens between Train/Test sets sometime.
	2. <b>High Bias & High Variance:</b> which shows your model has Low accuracy(performs very poor) and High variance in nature to predict unknown variable, or it may happens between Train/Test sets sometime.
	3. <b>Low Bias & Low Variance:</b> which shows your model fits as Expected and which is considered to be best-fit line, or it may happens between Train/Test sets.
	4.  <b>Low Bias & High Variance:</b> which shows your model has Good Accuracy but low variance, which needs to be tuned and reconsidered.

<p align="center">
  <img width="974" height="725" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Polynomial%20Regression/Reference/Bias_Variance_Tradeoff.JPG?raw=true">
</p>   

- Based on the above discussion we can find all the possible trade-offs as below. Below shown image is the model performance for the example that we have taken.

<p align="center">
  <img width="864" height="313" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Polynomial%20Regression/Reference/Bias_Variance_Tradeoff_plot.JPG?raw=true">
</p>   


### 3. Polynomial Regression in Python:
- [How to write your first PNR model using python](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Polynomial%20Regression/Polynomial%20Regression%20in%20Python.md#polynomial-regression-in-python)
- If you completed the above step, Congrats you have created your **PNR** machine learning model using Python.

### 4. Additional Use-cases:
1. Create a Machine Learning model to summarize trend between Acceleration and MPG.[[dataset.csv]](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Polynomial%20Regression/Dataset/carMPG.csv)
2. Create a Machine Learning model to summarize trend between Employee Position and Salary.[[dataset.csv]](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Polynomial%20Regression/Dataset/Position_Salaries.csv)
3. Create a Machine Learning model to predict Wine Quality.[[Wine Quality]](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Polynomial%20Regression/Dataset/winequality-red.csv)

##### Reference URL:
[Use case reference](https://github.com/ManikandanJeyabal/Workplace/tree/master/DataScience/Regression/Polynomial%20Regression)

##### Similar topics
1. [Simple Linear Regression](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/3-Regression%20Models/Simple%20Linear%20Regression#simple-linear-regression)
2. [Multiple Linear Regression](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/3-Regression%20Models/Multi%20Linear%20Regression#multi-linear-regression)