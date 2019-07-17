# Classification Models

### 1. What is Classification Models ?
- ***Classification*** is a technique where we categorize data into a given number of classes. The main goal of a classification problem is to identify the category/class to which a new data will fall under.
- Classification can be performed on ***structured*** or ***unstructured data***. 
- In statistics and machine learning, ***classification*** is the problem of identifying to which of a set of categories (sub-populations) a new observation belongs, on the basis of a training set of data containing observations (or instances) whose category membership is well-known.
- Classification is a simple example of ***pattern recognition***.
- In machine learning terminology, classification is considered an instance of supervised learning
  - **Ex:** learning where a training set of correctly identified observations is available
- The other hand corresponding unsupervised procedure is known as ***clustering***, and involves grouping data into categories based on some measure of inherent ***similarity or distance***.
- In classification algorithm, individual observations are analyzed into a set of quantifiable properties, known variously as **explanatory variables** or features.
- These properties may variously be as follows:
  - **Categorical:** [A, B, O, AB] for blood types. 
  - **real-value:** continues measurement of preasure in Steam engine. 
  - **integer-value:** No.of occurance of a word in given paragraph. 
  - **ordinal:** small, medium and large. 
- Classes are sometimes refered as targets or labels or categories.
- A smiple example of classification problem spam detection in email, which is a binary classification since there are only 2 classes as **spam** and **not spam**.

### 2. Why Classification Models ?
- As we know from the above definition of classification models, **The main goal of a classification problem is to identify the category/class to which a new data will fall under**.
- Classification Models are an essential part of Machine Learning and data mining applications. 
- Approximately 70% of real world problems in Data Science are classification problems.

### 3. Types of Classification Models
- There are several types of Classification models used in Machine Learning which falls under supervised learning, but we are going to see the below list of algorithms and its usecases widely in up-comming sessions. 
- Make yourself familier with the below list of names, because we are going to use them frequently in our course.
  - [Logistic Regression](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/CM_LGR/4-Classification%20Models/Logistic%20Regression/ReadMe.md#logistic-regression)
  - K-NN
  - [SVM - Support Vector Machine](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/CM_LGR/4-Classification%20Models/SVM#support-vector-machine)
  - Naive Bayes
  - [Decision Trees](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/CM_LGR/4-Classification%20Models/Decision%20Trees#decision-tree-classification)
    - [ID3](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/CM_LGR/4-Classification%20Models/Decision%20Trees/ReadMe-ID3.md#id3---iterative-dichotomizer-3)
    - [C4.5 or J4.8](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/CM_LGR/4-Classification%20Models/Decision%20Trees/ReadMe-C45.md#c-45-improved-version-of-id3)
    - [CART](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/CM_LGR/4-Classification%20Models/Decision%20Trees/ReadMe-CART.md#cart---classification-and-regression-tree)
  - [Random Forest Classification](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/CM_LGR/4-Classification%20Models/Random%20Forest#random-forest-classification)
