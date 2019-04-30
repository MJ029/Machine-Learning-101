# Simple Linear Regression

### 1 - Introduction
- Simple linear regression is a statistical method that allows us to summarize and study relationships(trend) between two continuous (quantitative) variables.
- We are going to learn the concept and basic procedures of simple linear regression.
- We will also learn two measures that describe the strength of the linear association that we find in data.

###### 1.1 - Things to Remember:    
  SLR -> Simple Linear Regression    
  MLR -> Multi Linear Regression    
  [Formula to find Mean](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/Formulas/Mean.JPG?raw=true)    
  [Formula to find Median](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/Formulas/Median.JPG?raw=true)

### 2 - What is Simple Linear Regression?
- As we seen earlier in introduction SLR is known as the following,
	- Simple linear regression is a statistical method that allows us to summarize and study relationships(trend) between two continuous (quantitative) variables.
	- One variable, denoted **X**, is regarded as the **predictor**, **explanatory**, or **independent variable**.
	- The other variable, denoted **y**, is regarded as the **response**, **outcome**, or **dependent variable**.
- SLR gets its adjective "simple," because it concerns the study of only one predictor variable.
- A simple key difference between SLR and MLR, is MLR gets its adjective "multiple," because it concerns the study of  two or more predictor variables.


### 2.1 - Types of Relationships:
- There are two types of relationships available one is  **deterministic (or functional) relationships** and second one is **statistical relationships**, simple linear regression will deals with second one.
	
###### 2.1.1 - Deterministic (or Functional) Relationships:
- One of the simple example to define deterministic relationship is the relationship between Celsius and Fahrenheit.
- Please find the below data points to understand the relationship.
- In deterministic relationships, the equation exactly describes the relationship between the two variables.

<p align="center">
  <img width="500" height="333" src="https://newonlinecourses.science.psu.edu/stat501/sites/onlinecourses.science.psu.edu.stat501/files/01simple/temps/index.jpg">
</p>
	

- Not: that the observed (x, y) data points fall directly on a line. As you may remember, the relationship between degrees Fahrenheit and degrees Celsius is known to be:

<p align="center">
	<b>Fahr = 9/5 Cels + 32</b><br>
</p>

- If you know the temperature in degrees Celsius, you can use this equation to determine the temperature in degrees Fahrenheit exactly.
- For each of these deterministic relationships, the equation exactly describes the relationship between the two variables.
- Some other examples of deterministic relationships:    
  - Circumference = π × diameter
  - **Hooke's Law:** Y = α + βX, where Y = amount of stretch in a spring, and X = applied weight.
  - **Ohm's Law:** I = V/r, where V = voltage applied, r = resistance, and I = current.
  - **Boyle's Law:** For a constant temperature, P = α/V, where P = pressure, α = constant for each gas, and V = volume of gas.

###### 2.1.2 - Statistical Relationships:
- In statistical relationship, the relationship between the variables is not perfect.
- The below example illustrate the relationship between response variable y is the mortality due to skin cancer (number of deaths per 10 million people) and the predictor variable x is the latitude (degrees North) at the center of each of 49 states in the U.S. [(dataset.csv)](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/Dataset/SkinCancer.csv)    
  <p align="center">
  	<img width="502" height="333" src="https://newonlinecourses.science.psu.edu/stat501/sites/onlinecourses.science.psu.edu.stat501/files/01simple/scatterplot_skin_cancer/index.png">
  </p>
- The above plot appears to be a negative linear relationship between latitude and mortality due to skin cancer, but the relationship is not perfect.
- Indeed, the plot exhibits some "trend," but it also exhibits some "scatter." Therefore, it is a statistical relationship, not a deterministic one.
- Based on the above observation if you lived in the higher latitudes of the northern U.S., the less exposed you'd be to the harmful rays of the sun, and therefore, the less risk you'd have of death due to skin cancer.
- Some other examples of statistical relationships might include:
	- Relationship between **Height and weight**, we all knows for each person height increases, you'd expect weight to increase, but not perfectly.
	- Relationship between **Speed and Mileage**, as driving speed increases, you'd expect gas mileage to decrease, but not perfectly.

### 3 - What is Best-Fitting Line ?
- In Definition, Line of best fit refers to a line through a scatter plot of data points that best expresses the relationship between those points.
- A straight line will result from a simple linear regression analysis of two or more independent variables.
- Since we are interested in summarizing the trend between two quantitative variables, we have to Find the Best-Fitting line for our equation.
- The Best-Fitting line must pass through the **Centroid**, (The point where the Mean of X and Mean of y meets each other)
- Equation for Best-Fit Line (or) Simple Linear Regression equation:


<p align="center">
	<b>y&#770;<sub>i</sub> = <i>b</i><sub>0</sub> + <i>b</i><sub>1</sub><i>x</i></b>
</p> 


- <b>y<sub>i</sub></b> is known as observed response for experimental unit <i>i</i>        
- <b>x<sub>i</sub></b> is known as predictor value for experimental unit <i>i</i>    
- <b>y&#770;<sub>i</sub></b> is known as predicted response (or fitted value) for experimental unit <i>i</i>    
- <b><i>b</i><sub>0</sub></b> is known as the Intercept or Constant, where line crosses the Vertical axis  
	- Formula to find Intercept:
<p align="center">
	<img width="130" height="48" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/Formulas/Intercept.JPG?raw=true">
</p>

- <b><i>b</i><sub>1</sub></b> Slope of the line
	- Formula to find Slope of the Line:
	- Here <b>X&#772;</b> is the Mean of X, and <b>y&#772;</b> is the Mean of y
<p align="center">
	<img width="226" height="77" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/Formulas/Slope.JPG?raw=true">
</p>

- If you want to find Intercept first you need to find Slope value then you can determine the intercept point.
- Steps to Remember when you are summarizing SLR, you have to follow these steps        
	- Find Mean <b>X&#772;</b> of Independent Variable <b>X</b>.
	- Find Mean <b>y&#772;</b> of Dependent Variable <b>y</b>.
	- Find Slope <b><i>b</i><sub>1</sub></b>.
	- Find Intercept <b><i>b</i><sub>0</sub></b>.
	- Finally find Best-Fit Line <b>y&#770;<sub>i</sub></b>.

##### 3.1 - Example: 
- The data-set used here is Bill Amount (vs) Tip Amount data-set [BillvsTip.csv](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/3-Regression%20Models/Simple%20Linear%20Regression/Dataset/BillTip.csv), we are going to predict the Best-Fit line for the problem.    
- Please refer the below chat to find the solution for each step, which will give us the value for <b><i>b</i><sub>1</sub></b> Slope is <b>0.146</b> and value for <b><i>b</i><sub>0</sub></b> Intercept is <b>-0.802</b>

<p align="center">
  	<img width="906" height="178" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/References/Tabular-BillvsTip.JPG?raw=true">
</p>

- By obtaining the values for <b><i>b</i><sub>1</sub></b> and <b><i>b</i><sub>0</sub></b> we can now find the Best-Fit line of our problem, please find the below image. and we can see here our Best-Fit line of the prediction line is passing through the <b>Centroid (74, 10)</b>.

<p align="center">
  	<img width="419" height="296" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/References/BillvsTip.JPG?raw=true">
</p>

- Since the SLR will tell you the statistical relationship between two variables which is not perfect. we can see some Error in our Model
- In the above Example the Predicted value is not accurate it has some difference on it which is known as <b>"prediction error"</b> (or <b>"residual error"</b>).
- As you can see, the size of the prediction error purely depends on the data point.
- The size of the prediction error here is for <b>X<sub>1</sub></b> is 5 - 4.12 = 0.8.
- Now we have our predicted values in our hand so what is the next step, there is a thumb rule in summarizing the Best-Fit line and that is "always minimize the sum of the squared prediction errors". One way to achieve this goal is to invoke the "least squares criterion".
- So keep in mind the thumb rule, a line that fits the data "best" will be one for which the n prediction errors are as small as possible in some overall sense.
- Formula to Sum of Squared Error or Sum of Squared Residual is:

<p align="center">
  	<img width="157" height="78" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/Formulas/sum%20of%20the%20squared%20residual%20errors.JPG?raw=true">
</p>
 
### 4 - Determination of r-square(Accuracy):
- Now we got the information need to calculate the Accuracy of our model.
- <b>SSR</b> is the "regression sum of squares" and quantifies how far the estimated sloped regression line, <b>y&#770;<sub>i</sub></b>, is from the horizontal "no relationship line," the sample mean or <b>y&#772;</b>.
- <b>SSE</b> is the "error sum of squares" and quantifies how much the data points y<sub>i</sub>, vary around the estimated regression line, y&#770;<sub>i</sub>
- <b>SST</b> is the "total sum of squares" and quantifies how much the data points, y<sub>i</sub> vary around their mean, <b>y&#772;</b>
- Note:
	- <b>SSR => (y&#770;<sub>i</sub> - <b>y&#772;</b>)<sup>2</sup> => 89.925</b>
	- <b>SSE => (y<sub>i</sub> - <b>y&#770;<sub>i</sub></b>)<sup>2</sup> => 30.075</b>
	- <b>SST => (y<sub>i</sub> - <b>y&#772;</b>)<sup>2</sup> => 120</b>
	- <b>SST = SSE + SSR => 30.075 + 89.925 = 120</b>

- Formula to find <b>r<sup>2</sup></b>:
	- <b>r<sup>2</sup> = SSR/SST => 89.925/120 = 0.749</b>
	- This is know ans the Accuracy of Our Prediction.

##### 4.1 - Model Summary:
- Please find the Model summary for our Prediction problem below.

<p align="center">
  	<img width="562" height="347" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/References/BillvsTipSummary.JPG?raw=true">
</p>


### 5 - Simple Linear Regression in Python:
- [How to write your First Program in Python](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/Simple%20Linear%20Regression%20in%20Python.md)
- If you completed the above step, Congrats you have created your first machine learning model using Python.
- Still worried how it is a machine learning ? here is your answer, in the above program you have created a model(machine) that learned from its input IV and predicted result.

### 6 - Additional Use-cases:
1) Create a Machine Learning model in python to summarize trend between [Employee Yrs of Experience (vs) Salary]. [[dataset.csv]](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/Dataset/Salary_Data.csv)   
2) Create a Machine Learning model in python to summarize trend between [Latitude (vs) Skin Cancer Morality].
[[dataset.csv]](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/Dataset/SkinCancer.csv)    
3) Create a Machine Learning model in python to summarize trend between [Height (vs) Weight].[[dataset.csv]](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/Dataset/Book1.csv)   
4) Create a Machine Learning model in python to summarize trend between [Age (vs) Blood Fat].[[dataset.csv]](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/Dataset/BloodFatCalculator.csv)   
5) Create a Machine Learning model in python to summarize trend between [Kilowatts (vs) Bill Units].[[dataset.csv]](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Simple%20Linear%20Regression/Dataset/ElectricityCalculator.csv)

##### Reference URL:    
  [To Understand Concepts Behind SLR - Site](https://newonlinecourses.science.psu.edu/stat501/node/250/)    
  [To Understand Concepts Behind SLR - Video](https://www.youtube.com/playlist?list=PLIeGtxpvyG-LoKUpV0fSY8BGKIMIdmfCi)    
  [Use-case Solution Reference](https://github.com/ManikandanJeyabal/Workplace/tree/master/DataScience/Regression/Simple%20Linear%20Regression/)
