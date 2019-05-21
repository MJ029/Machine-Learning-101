# Decision Tree Regression in Python:

### 1 - Prerequisites:    
  - Basics of Numpy    
  - Basics of Pandas    
  - Basics of sklearn.tree.DecisionTreeRegressor
  - Basics of sklearn.preprocessing.LabelEncoder

***Notes:*** for your understanding I'm using the same Example used in Step-by-Step Demonstration.
### 2 - Import Libraries:
- If you want to write your own program to predict Polynomial Regression you need to import the needed libraries first.
- The below libraries are used in this program demonstration.
```py
import pandas as pd
from sklearn.preprocessing import LabelEncoder
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeRegressor
```


### 3 - Import Data-set with LabelEncoding:
- Importing our data-set is the next step, once we imported our data-set we need to identify Independent Variable(IV) and Dependent Variable(DV) out of data-set.
- Here we are using **Pandas** library to Import our data-set from the directory, it is recommended to keep the data-set in same directory where the python file is saved.
- This time before converting a DF to ND.array we are going to perform Categorical Encoding process. and for this we are going to use the below code ``` df[cat_cols] = df[cat_cols].apply(lambda col: lbl_encoder.fit_transform(col)) ``` which converts categorical values in a DF to numeric values
- We are specifying required No.of rows and columns using pandas.iloc method.
- Here in **[:, :-1]**, **:** refers to fetch all rows from our data-set and **:-1** refers to fetch all columns other than last column, since we have only one column as IV in our data-set will fetch only one ndArray as **X**
- **pandas.iloc.values** will actually fetch and load values from data-set to variable **X and y**.

```py
df = pd.read_csv('Dataset.csv')

lbl_encoder = LabelEncoder()
cat_cols = ['Outlook', 'Temp', 'Humidity', 'Windy']
df[cat_cols] = df[cat_cols].apply(lambda col: lbl_encoder.fit_transform(col))

X = df.iloc[:, :-1].values
y = df.iloc[:, -1].values
```

### 4 - Split Data into Training set and Test Set:
- Once we got our IV and DV, it is recommended to Split your data in to Training set and Test Set.
- But in our case our ID and DV contains only 6 rows we are not doing this step as of now for this Example, But please find the Below code to split your IV and DV.

```py
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
```

### 5 - Fit & Predict Model:
- Once our data set is spitted as **X_train, y_train and X_test, y_test** we can start our model fitting.
- To Fit our model we are going to use **DecisionTreeRegressor** from **sklearn.tree**
- **Please refer the Documentation page to see the List of parameters it will accept.**
- once we created our model we need to fit it using .fit Method, that's it the fit method will do everything for you, simply we can call predict method to find predicted values

```py
regressor = DecisionTreeRegressor()
regressor.fit(X_train, y_train)
y_pred = regressor.predict(X_test)
```