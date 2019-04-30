# SVR - Support Vector Regression

##### Notes: 
- Please remember the below list of words in your mind before getting into the Session.
	1. hyper-plane.
	2. Margins.
	3. Support Vectors.
	4. Kernal.
	5. SVM = Support Vector Machine.
	6. SVR = Support Vector Regression

### 1. Introduction
- Hi Welcome to 4'th part of Regression models - **Support Vector Regression[SVR]** which is sub class of a familiar ML-Model **Support Vector Machine[SVM]**.
- I recommend you to look in to [SVM-Support Vector Machine](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/Python%20%2B%20Machine%20Learning%20%2B%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/4-Classification%20Models/SVM#support-vector-machine) intution to get more understanding on SVR.
- The Support-Vector algorithm is a nonlinear generalization of the Generalized Portrait algorithm, it is firmly grounded in the framework of statistical learning theory, or VC theory.
- In a nutshell, VC theory characterizes properties of learning machines which enable them to generalize well to unseen data.
-  Our goal is to find a function f(x) that has at most <b>ε</b> deviation from the actually obtained targets <b>y<sub>i</sub></b> for all the training data, and at the same time is as flat as possible.
-  It is considered a non parametric technique because it relies on kernel functions.
-  In other words, we do not care about errors as long as they are less than **ε**, but will not accept any deviation larger than this
-  The key difference between SVM and SVR is that SVM works with non-linear(Discrete) data in the other hand SVR works with Linear(continuous) data.
-  When it comes to SVR the following terms used very frequently
	1.  Kernal:
		1. The function which is used to map lower dimentional data into a higher dimentional data.
		2. Generally it could be linear, polynomial, sigmoid and rbf.
		3. This is known as Kernel-trick. 
	2.  Support Vectors:
		1. Actual data-points which are close to line of boundary.
		2. The distance between data-point and boundary line
	3.  Hyper Plane:
		1. In SVM, Hyper Plane is the important factor which separates the data classes, on we can say it the line between data classes.
		2. In SVR, Hyper Plane will play the same role as SVM, but as we discussed before the key change is, here it is a line between linear(continuous) data.
		3. We can consider this as a best fit line predicted by our kernal.
	4.  Boundary Plane or Decision Boundary(margin of tolerance):
		1. The name Boundary itself defines its usage, yes it is going to define the upper/lower boundaries from the Hyper-Plane.
		2. It act as a margin between Hyper-Plane and data points. One interesting factor is The support vectors can be on the Boundary line or outside boundary line.
		3. Here the distance between Boundary-Plane and Hyper-Plane are considered as epsilon(<b>ε</b>) distance. So the lines that we draw are at ‘<b>+ε</b>’ and ‘<b>-ε</b> ’ distance from Hyper Plane.
		4. Below image shows the above points discussed.

<p align="center">
  <img width="500" height="333" src="http://www.saedsayad.com/images/SVR_2.png">
</p>
<p align="center">
	<b> Ref: http://www.saedsayad.com/support_vector_machine_reg.htm </b>
</p>

- Why SVR and how it differs from Linear Regression ?
	- In Normal Linear Regression model's like (SLR, MLR and Poly), we tried to mimize the error rate and we derived our best fit line.
	- In SVR, we tried to fit the error within the boundary threshold, so we can get more accuracy and better prediction in our model.

### 2. Support Vector Regression in Python:
- [How to Write your first program in Python](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/Python%20%2B%20Machine%20Learning%20%2B%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/3-Regression%20Models/Support%20Vector%20Machine/Support%20Vector%20Regression%20In%20Python.md#support-vector-regression-in-python)
- If you completed the above step, Congrats you have created your **SVR** machine learning model using Python.

### 3. Additional Use-cases:
1. Create a Machine Learning Model to predict Car Price and compare your results with Multi-Linear and Polynomial results.[[Car Price Prediction]](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/Python%20%2B%20Machine%20Learning%20%2B%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/3-Regression%20Models/Support%20Vector%20Machine/Dataset/Car_Price_Prediction.csv)
2. Create a Machine Learning Model to predict Air Quality.[[Air Quality]](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/Python%20%2B%20Machine%20Learning%20%2B%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/3-Regression%20Models/Support%20Vector%20Machine/Dataset/AirQualityUCI.csv)
3. Create a Machine Learning model to predict ERP-estimated relative performance of a computer and compare it with Multi-Linear and Polynomial results.[[ERP Prediction]](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/Python%20%2B%20Machine%20Learning%20%2B%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/3-Regression%20Models/Support%20Vector%20Machine/Dataset/ERP_Prediction.csv)
4. Create a Machine Learning model to predict Wine Quality using SVR.[[Wine Quality]](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/Python%20%2B%20Machine%20Learning%20%2B%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/3-Regression%20Models/Support%20Vector%20Machine/Dataset/winequality-red.csv)


##### Reference URL:
[Use Cases reference](https://github.com/ManikandanJeyabal/Workplace/tree/master/DataScience/Regression/Support%20Vector%20Machine)   
[SVM - Support Vector Machine](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/Python%20%2B%20Machine%20Learning%20%2B%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/4-Classification%20Models/SVM#support-vector-machine)  
[How Does SVR Works](https://www.quora.com/How-does-support-vector-regression-work)  
[how does support vector regression work intuitively](https://stats.stackexchange.com/questions/82044/how-does-support-vector-regression-work-intuitively)

##### Similar Topics:
[1. Simple Linear Regression](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/Python%20%2B%20Machine%20Learning%20%2B%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/3-Regression%20Models/Simple%20Linear%20Regression#simple-linear-regression)   
[2. Multi Linear Regression](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/Python%20%2B%20Machine%20Learning%20%2B%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/3-Regression%20Models/Multi%20Linear%20Regression#multi-linear-regression)   
[3. Polynomial Regression](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/Python%20%2B%20Machine%20Learning%20%2B%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/3-Regression%20Models/Polynomial%20Regression#polynomial-regression)  
[4. Decision Tree Regression]()  
[5. Random Forest Regression]()  
