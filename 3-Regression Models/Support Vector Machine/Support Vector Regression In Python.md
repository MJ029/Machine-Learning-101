# Support Vector Regression in Python

### 1 - Prerequisites:    
  - Basics of Numpy    
  - Basics of Pandas          
  - Basics of matplotlib.pyplot
  - Basics of sklearn.preprocessing.StandardScaler
  - Basics of sklearn.model_selection.train_test_split
  - Basics of sklearn.metrics
  - Basics of sklearn.svm.SVR

### 2 - Import Libraries:
- If you want to write your own program to predict Polynomial Regression you need to import the needed libraries first.
- The below libraries are used in this program demonstration.
```py
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from sklearn import preprocessing, model_selection, metrics
import statsmodels.api as sm
from sklearn.svm import SVR
```

### 3 - Import Data-set:
- Importing our data-set is the next step, once we imported our data-set we need to identify Independent Variable(IV) and Dependent Variable(DV) out of data-set.
- Here we are using **Pandas** library to Import our data-set from the directory, it is recommended to keep the data-set in same directory where the python file is saved.
- Here from Pandas data-set we are directly creating our X(IV) and y(DV).
```py
df = pd.read_excel('AirQualityUCI.xlsx')
```

### 4 - Handle Missing Data:(Optional)
- Our data-ser contains missing data in the form of (-200) default value. so we are going to handle this in Dataframe itself.
- To know more about how to handle Missing value in numpy.ndArray [click here](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/2-Data%20Pre-Processing#1-handling-missing-data) to see.
- In this Function we are taking a pandas Dataframe as input and returning pandas Dataframe as output
- First we are filtering colum belong to **Object, float64, int64** and for that Dtype columns only we are going to apply missing value
- For our case we are considering **most_frequent** value as replacement value. and if most occured value itself missing value means we are considering 2'nd most occured value of the column. 
```py
def replaceUnsupportedValues(df):
    for column in df:
        print("Iterating Column: --> ", column)
        if df[column].dtype in ('object', 'float64', 'int64'):
            if (df[column] == -200).any():
                print("Replace Found...")
                most_occ = df[column].mode()[0]
                print("Most Occured Value Before-->", most_occ)
                if most_occ == -200:
                    most_occ = df[column].value_counts().head(2).iloc[[1]].idxmax()
                    print("Most Occured Value After-->", most_occ)
                df[column] = df[column].replace(-200, most_occ)
    return df

df = replaceUnsupportedValues(df)
```

### 5. Create Matrix of Features X and dependent variable y:
- To convert pandas dataframe to X and y, use the following code.
```py
X = df.iloc[:, :-1].values.astype(np.float64)
y = df.iloc[:, -1].values.astype(np.float64)
```

### 6. Feature Scaling:(Optional)
- This step is optional, if you data-set having Dependent/Independent Variable dominating other then we have to perform feature scaling.
- We have already imported the StandardScaler class.
```py
sc_X = StandardScaler()
X = sc_X.fit_transform(X)
``` 
- Please [click here](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/2-Data%20Pre-Processing#4-feature-scaling) to know how to handle Feature Scaling in your problem.

### 7. Apply Backward Elemination to statistically significant variables:(Important and Automated Way)
- One of the Important and difficult step in Regression model when we are having morethan 2 Independent variables is to check whether we are falling in to dummy varibale trap. to ensure this we included the following step which will consider only **statistically significant variables**
```py
#Backward Elimination
def backwardElimination(x, sl, y, features):
    numVars = len(x[0])
    for i in range(0, numVars):
        regressor_OLS = sm.OLS(y, x).fit()
        maxVar = max(regressor_OLS.pvalues)
        if maxVar > sl:
            for j in range(0, numVars - i):
                if (regressor_OLS.pvalues[j].astype(float) == maxVar):
                    print("Removing Column --> ", features[j])
                    features = np.delete(features, j, 0)
                    x = np.delete(x, j, 1)
    print(regressor_OLS.summary())
    print("Remaining Features --> ",features)
    return x

SL = 0.05
X_stats = sm.add_constant(X)
X_features = df.columns.values.astype(str)
X_features = np.delete(X_features, -1, 0)
X_features = np.append(['constant'], X_features, axis=0)
X_Opt = X_stats[:, :]
X = backwardElimination(X_Opt, SL, y, X_features)
```
- In the above code we are creating a function which will take a set on input parameters as follows
  1. Matrix of Feattures - X
  2. Significance Level
  3. Dependent Variable - y
  4. Column List (Optional)
- Here we are using OLS model from statsmodel library to get the **statistically significant variables** from OLS Summary and remove it if exceds Significance level.
- Finally we are returning our Matrix of features X for further process.

### 8. Split Train/Test:
- The next step is to split of Matrix of Features X to Train and Test sets and to do that please use below command.
```py
X_train, X_test, y_train, y_test = model_selection.train_test_split(X, y, test_size=0.2, random_state=1)
```

### 9. Create SVR Model:
- The nex tstep is to create a regressor of SVR and to do this we are going to use a class called ```SVR``` from library ```sklearn.svm```. Which takes several parameters like **epislon, C, kernel, degree, gammma**. [click here]() to see the full details aboout the parameter or if you are in spyder click CTRL+I after the name SVR.
```py
regressor = SVR()
regressor.fit(X_train, y_train)
```

### 10. Determine Model Accuracy:
- Use the below code to check the model accuracy.
```py
RSME_Train = np.sqrt(metrics.mean_squared_error(y_train,regressor.predict(X_train)))
print(RSME_Train)
Score_Train = regressor.score(X_train, y_train)
print(Score_Train)
```

### 11. Automating Full Flow with various Kernels:(Optional)
- Sometimes you have to run your data-set with more than one kernel and use the Optimized result for your model, and to do that please find the below code.
```py
C_Value = 30
kernels = ['rbf','poly', 'sigmoid', 'linear']
for k in kernels:
    for i in range(1, C_Value+1):
        regressor = SVR(C=i, kernel=k)
        regressor.fit(X_train, y_train)    
        RSME_Train = np.sqrt(metrics.mean_squared_error(y_train,regressor.predict(X_train)))
        Score_Train = regressor.score(X_train, y_train)
        print("Kernel: ", k, "Ittr: ", i, " RSME: ", RSME_Train, " Score: ", Score_Train)
```
- change the kernel order and C_Value according to your usecase.
