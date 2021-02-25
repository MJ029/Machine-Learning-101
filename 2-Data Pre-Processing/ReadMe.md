# Data Pre-processing

- Data Pre-Processing is one of the important task in Machine/Deep Learning field.
- Pre-processing refers to the transformations applied to our data before feeding it to the algorithm.
- Data Pre-processing is a technique that is used to convert the raw data into a clean data-set. In other words, whenever the data is gathered from different sources it is collected in raw format which is not feasible for the analysis.
- To achieve a best result in the applied model in Machine Learning projects the format of the data has to be in a proper manner. 
- For Example:
	- ***Random Forest*** algorithm **does not support null** values, therefore to execute random forest algorithm null values have to be managed from the original raw data set. 
	- This is know as Missing data Handling in data Pre-processing.
- Another aspect is that data set should be formatted in such a way that more than one Machine Learning and Deep Learning algorithms are executed in one data set, and best out of them is chosen.
- In this part you will learn most commonly used techniques in data Pre-processing and how to get in handy with them. Data Pre-processing has the following stages:
	1. [Handling Missing Data](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/2-Data%20Pre-Processing#1-handling-missing-data)
	2. [Handling Categorical Data](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/2-Data%20Pre-Processing#2-handling-categorical-data)
	3. [Splitting Data-Set into Dev/Training/Test set](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/2-Data%20Pre-Processing#3-spiting-your-data-set-into-devtrainingtest-set)
	4. [Feature Scaling](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/2-Data%20Pre-Processing#4-feature-scaling)

### 1. Handling Missing Data
- As all we know the term Missing data refers to the data actually not available in the expected field or available as Null or empty. if we are not addressing this issue with high priority your machine learning model will give poor prediction result.
- So we need to be equipped to handle the problem when we come across them.
- We can see multiple suggestions and ways in internet to address this problem, but one of the thumb rule in machine learning is Every record is important and we don't know some information belongs to that row may be an important key factor for our prediction.
- So we are going to take one of the most common idea to handle the problem is to take a Mean/Median/Most occurred of all the values from the column and replace it with missing data.
- ***Imputer*** is a class from Sci-kit Learn library.Pre-perocessing which is going to do the task, exactly it is going to do above step.
- It has the following input parameters
	1. **missing_values:**
		- It accepts valeus like integer, string, np.nan(default) or None. 
		- Based on your usecase you can go with either of'em. at the initial phase of data pre-processing it is recommended to go with NaN or np.nan.
	2. **strategy:**
		- It is an optional field
		- By default will take mean of the column
		- If Mean --> then replace missing values using the mean along each column and it Can only be used with numeric data.
		- If Median --> then replace missing values using the median along each column. Can only be used with numeric data.
		- If most_frequent --> then replace missing using the most frequent value along each column. Can be used with strings or numeric data.
		- If constant --> then replace missing values with fill_value. Can be used with strings or numeric data.
	3. **Axis:**
		- The axis along which to impute.
		- By default it is 0
		- If axis=0, then impute along columns.
		- If axis=1, then impute along rows.
	4. It has some other input parameters like verbose and copy, based on your use case you can choose it. the above 2 are the most frequently used input arguments. If you want to know more about Imputer Please visit the following Link [sklearn.preprocessing.Imputer](https://scikit-learn.org/stable/modules/generated/sklearn.impute.SimpleImputer.html).    
	**Note:** Please check for the current version of Imputer before reading it.
```py
from sklearn.preprocessing import Imputer 			# module import: importing the file Impurter from sklearn.proprocessing package
imputer = Imputer(missing_values = "NaN", strategy = "mean") 	# Creating object of the class
```
- Once we have completed the above 2 steps we can either do fit and transform separately or simply we can call fit_transform method from Imputer to fill the missing values with relevant information.
```py
imputer = imputer.fit(X[:,1:3])  		# Will fit our Independent Variable X.
X[:, 1:3] = imputer.transform(X[:, 1:3]) 	# Will Transform Missing variable with relevent value.
or	
X[:, 1:3] = imputer.fit_transform(X[:, 1:3]) 	# will do above 2 steps in single step.
```
- The code above will fit_transform the Imputer object to our matrix of features X. Since we used **(:)**, it will select all rows and **(1:3)** will select the second and the third column.
	
### 2. Handling Categorical Data
- Sometimes our data is in qualitative form, that is we have texts as our data.
- Now it gets complicated for machines to understand texts and process them, rather than numbers, since the models are based on mathematical equations and calculations.
- We cannot convert all the data from text form to numeric, expect some like categorical data. therefore we have to encode the categorical data, examples of categorical data we may expect in our data-set are Country, Department, Gender and any key which will place Group by Aggregation operation in your problem.
- ***LabelEncoder*** and ***OneHotEncoder*** are a classes form Sci-kit Learn library, which is going to do the task, exactly it is going to do what we have mentioned in above step.

#### 2.1 [LabelEncoder:](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.LabelEncoder.html)
- It is mainly used to convert Categorical variables into a sequence of numbers like 0, 1, 2, 3, 4, 5 and etc.. based on the upper limit.
- It is important to remember that the index starts from 0 and ends with upper limit.
- Once the encoding is done we can see our encoded data, to perform the task, run the below command.
```py
from sklearn.preprocessing import LabelEncoder, OneHotEncoder 	# module import: importing the file LabelEncoder, OneHotEncoder from sklearn.proprocessing 
label_Encoder = LabelEncoder() 					# Creating Object of the class to perform our task
X[:,0] = labelencoder_X.fit_transform(X[:,0]) 			# 0 represents the Encoding column index.
```
- The above code will select all the rows (because **:**) of the first column (because **0**) and fit the LabelEncoder to it and transform the values.
- Here we will create a new problem if there are more than two categories.
- As we keep assigning different integers to different categories, it may create a confusion for the algorithm to learn the Relationship(trend) between variables, to solve this problem we are going to use OneHotEncoder.

#### 2.2 [OneHotEncoder:](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.OneHotEncoder.html)
- It is recommended to have this in pipeline after LabelEncoder completed.
- The transformation behind OneHotEncoder is very simple it follows the operation of Binary Transformation, hope you might remembered the relationship between integer to Binary format.
- Here we are going to convert the values encoded using LabelEncoder to Binary form.
- It has an important parameter called categorical_features to accomplish the task.
- By running the below code in our data-set, it will select the first column to OneHotEncode the categories.
- Then simply calling fit_transform method will do the remain for us.
```py
onehotencoder = OneHotEncoder(categorical_features =[0]) 	# Applying OneHotEncoding to index 0
X = onehotencoder.fit_transform(X).toarray() 			# loading the converted values to variable X.
```
- If you check your data-set now, all your categories will have been encoded to **0's** and **1's**.   
- This process is also know as creating Dummy Variables. But still we have a problem here due to the newly added columns, yes it will create a problem called "Dummy variable trap". It is important to avoid dummy variable trap on our data-set, to avoid this it is recommended to remove last column which is generated. we will see more about Dummy variable trap in Multi Linear Regression.
	
### 3. Spiting your data-set into Dev/Training/Test set
- It is recommended to split your data-set to Dev/Training/Test sets to complete our development, training and Tests.
- Usually in internet you can find only Training/Test set separation only, you can follow any method. for your understanding we are going to use only Training/Test separation only.
- We will train our machine learning models on our training set, i.e our machine learning models will try to understand any correlations in our training set and then we will test the models on our test set to check how accurately it can predict.
- A general rule of the thumb is to allocate **80% of the data-set to training set and the remaining 20% to test set**.
- ***test_train_split*** is a class of sklearn.model_selection library, which is going to do the task.
```py
from sklearn.model_selection import train_test_split 			# module import: importing the file train_test_split from sklearn.proprocessing 
X_train, X_test, Y_train, Y_test = train_test_split(X,Y, test_size=0.2) # Creating 4 variable for training set and test set.
```
- The above code will split out data-set into training and test set based on 80/20 ratio. and will assign the data into 4 new variables called X_train, X_test, Y_train, Y_test.
- For our understanding we are using the name as X_train, X_test, Y_train, Y_test. you can keep any name based on your understanding.
- Train-test spliter has more input variables, please refer sklearn documentation page for more info.

### 4. Feature Scaling
- The final step of data Pre-processing is to apply the very important feature scaling.
- Feature scaling is a method used to standardize the range of independent variables or features of data. 
- Why it is important:
	- A lot of machine learning models are based on Euclidean distance.
	- For example, the values in one column (x) is much higher than the value in another column (y), (x2-x1) squared will give a far greater value than (y2-y1) squared.
	- It shows clearly that one square difference dominates over the other square difference.
	- In the machine learning equations, the square difference with the lower value in comparison to the far greater value will almost be treated as if it does not exist.
	- That is why it is necessary to transform all our variables into the same scale.
- How to Scale Features:
	- There are 4 common methods available to completed the task
		1. **Standardisation**:
			- Standardisation replaces the values by their Z scores.
			- This redistributes the features with their mean **μ=0** and standard deviation **σ=1** .
			- This method is widely used for normalization in many machine learning algorithms like **support vector machines, logistic regression, and artificial neural networks**
			- Steps:
				- Determine the distribution mean and standard deviation for each feature.
				- Subtract the mean from each feature.
				- Divide the values (mean is already subtracted) of each feature by its standard deviation.
				- <b>x</b> is the original feature vector, <b>x&#772; = average(x)</b> is the mean of that feature vector and  <b>&sigma;</b> is its standard deviation.
				<p align="center">
  					<img width="161" height="82" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/2-Data%20Pre-Processing/Reference/Standardisation.JPG?raw=true">
				</p>
		2. **Mean Normalisation**:
			- This distribution will have values between **-1 and 1** with **μ=0**.
			- <b>x</b> is the original value, <b>x'</b> is the normalized value.
			- **Standardisation** and **Mean Normalization** can be used for algorithms that assumes zero centric data like **Principal Component Analysis(PCA)**.
			<p align="center">
  				<img width="272" height="105" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/2-Data%20Pre-Processing/Reference/Mean%20Normalization.JPG?raw=true">
			</p>
		3. **Min-Max Scaling(Rescaling)**:
			-  is the simplest method and consists in rescaling the range of features to scale the range in **[0, 1] or [−1, 1]**.
			- Selecting the target range depends on the nature of the data.
			<p align="center">
  				<img width="284" height="95" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/2-Data%20Pre-Processing/Reference/Min-Max%20Scaling.JPG?raw=true">
			</p>
		4. **Unit Vector**:
			- Scaling is done considering the whole feature vecture to be of unit length.
			- **Min-Max** Scaling and **Unit Vector** techniques produces values of **range [0,1]**. 
			- When dealing with features with hard boundaries this is quite useful.
			- For example, when dealing with image data, the colors can range from only 0 to 255.
			<p align="center">
  				<img width="178" height="94" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/2-Data%20Pre-Processing/Reference/Unit%20Vector.JPG?raw=true">
			</p>
- Some examples of algorithms where feature scaling matters are:
	- ***k-nearest neighbors*** with an Euclidean distance measure is sensitive to magnitudes and hence should be scaled for all features to weigh in equally.
	- ***Principal Component Analysis (PCA)*** tries to get the features with maximum variance and the variance is high for high magnitude features. This skews the PCA towards high magnitude features.
	- We can speed up gradient descent by scaling. This is because θ will descend quickly on small ranges and slowly on large ranges, and so will oscillate inefficiently down to the optimum when the variables are very uneven.
	- Algorithms like Linear Discriminant Analysis(LDA), Naive Bayes are by design equipped to handle this and gives weights to the features accordingly. 
- We are going to take Standardization for our feature scaling task.
- ***[StandardScaler](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html)*** is a class of sklearn.preprocessing library, which is going to do the task.
```py
from sklearn.preprocessing import StandardScaler 	# module import: importing the file StandardScaler from sklearn.proprocessing  								# Creating Object of the class to perform our task
sc_X = StandardScaler()
X_train = sc_X.fit_transform(X_train)
X_test = sc_X.transform(X_test)
``` 
**Note**: The above step is required when you have too large values Predictor/Independent variable.   
**FAQ**: Feel free to Drop your queries in Issues, will be addressed ASAP
