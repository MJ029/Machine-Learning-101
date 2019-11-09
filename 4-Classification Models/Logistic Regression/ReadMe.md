# Logistic Regression

#### Points to Remember
- IV = Independent Variable
- DV = Dependent Variable
- LR = Logistic Regression
- Confusion Matrix [True Positive, True Negative, False Positive, False Negative]
- F1-Score [Precision, Recall]
- Prediction Regions

### 1. Introduction:
- Hi All, Welcome to 2'nd module of our course where we are going to see more and more about the Classification problems.
- As we know earlier, Approximately 50-70% of problems in Data Science are classification problems which is used in machine learning and data mining area.
- Logistics Regression is common and mostly used regression method for solving the binary classification problem such as spam/gender/cancer detection, etc...
- In binary classification the outcome or target variable is dichotomous in nature. Dichotomous means there are only two possible classes.
- Logistic Regression can be used as the baseline for any binary classification problem. since it estimates the relationship between one dependent binary variable and independent variables.
- One of the important point to remember here is a special case of linear regression where the target variable is categorical in nature.
- Logistic Regression using logit function to predicts the probability of occurrence of a binary event[target variable].

#### 2. Logistic Regression Intuition:
##### 2.1 Assumption:
- The thumb rule of logistic regression in simple as mentioned in 2 steps:
- Step-1:
	- Take a Linear equation, Here linear equation is nothing but your linear model.  
- Step-2:  
	- Find the probability of occurrence of the linear equation for the given data-point.  
	- To find the probability of the equation we need to apply sigmoid function on the Linear Equation.    

##### 2.1 Sigmoid Function[logistic function]:
- It gives an ‘S’ shaped curve that can take any real-valued number and map it into a value between 0 and 1. 
- y = 1, If curve goes to positive infinity.
- y = 0, If curve goes to negative infinity.
- If output of sigmoid function > 0.5, then we can classify the outcome as 1 or YES.
- If output of sigmoid function < 0.5, then we can classify the outcome as 0 or NO.


##### 2.2 Diff between Logistic Regression and Linear regression:
- Linear Regression:
	- Output is interval/continuous[Linear in nature].
	- Examples are house price and truck mileage prediction.
	- It is estimated using Ordinary Least Squares (OLS).
	- Data needs to be normally distributed.
	- It violates definition of probability.
- Logistic Regression:
	- Output is discrete/Constant[ex: (0 or 1) and (yes or no)].
	- Examples are spam/gender/cancer detection.
	- It is estimated using Maximum Likelihood Estimation (MLE).
	- Data not required to be normally distributed.
	- It does not violates definition of probability.
	- Probabilities are often not linear.

##### 2.3 Estimation:
- The dependent variable in logistic regression follows Bernoulli Distribution and estimation is done through Maximum Likelihood.
- since we are using Maximum Likelihood, there is no concept of R Square, Model fitness is calculated through Concordance, KS-Statistics and etc...
- Maximum Likelihood Estimation[MLE]:
	- It is a maximization method, it determines the parameters that are most likely to produce the observed data. 
	- In statistical, MLE sets the mean and variance as parameters in determining the specific parametric values for a given model.
	- It assumes a joint probability mass function.
- Least Square Method[LSM]:
	- It is a distance-minimizing approximation method.
	- In [OLE - Ordinary Least Squares], estimates are computed by fitting a regression line on given data points that has the minimum sum of the squared deviations (least square error). 
	- It doesn't require any stochastic assumptions for minimizing distance.

##### 2.4 Types of Logistic Regression:
- Binary Logistic Regression:   
	- Target variable is binary.
	- Ex:  
		Spam or Not Spam   
		Cancer or No Cancer   
		Male or Female
- Multinomial Logistic Regression:
	- The target variable has three or more nominal categories[without ordering]
	- Ex:  
		Predicting the blood types.

- Ordinal Logistic Regression:
	- The target variable has three or more ordinal categories[with ordering]
	- Ex:  
		find Rating from 1-5.

#### 3. Logistic Regression Equation:
- We all saw the thumb-rule of logistic regression in Assumptions, we can state as below.
- **The Natural logarithm of the odds ratio is equivalent to a linear function of the independent variables**. This statement gives below equation.

<p align="center">
  <img width="473" height="117" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/CM_LGR/4-Classification%20Models/Logistic%20Regression/references/Fig-1.JPG?raw=true">
</p> 


- Taking anti-log on both the side will allow us to find the estimated regression equation.

<p align="center">
  <img width="432" height="532" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/CM_LGR/4-Classification%20Models/Logistic%20Regression/references/Fig-2.JPG?raw=true">
</p> 

<p align="center">
  <img width="315" height="165" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/CM_LGR/4-Classification%20Models/Logistic%20Regression/references/Fig-3.JPG?raw=true">
</p> 

- By applying the above equation for each independent variable in your data set you will get the predicted variable 


