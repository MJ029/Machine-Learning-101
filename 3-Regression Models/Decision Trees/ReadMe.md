# Decision Tree Regression


### Points To Remember:
  - D-Tree
  - Attribute - IV
  - Target Variable - DV
  - SD = Standard Deviation
  - SDR = Standard Deviation Reduction
  - ID3 = Iterative Dichotomiser 3

### 1. Introduction:
- Hi, Welcome to 5'th part of Regression Models. Here we are going to see in-detail about Decision Tree Algorithms for Regression problems.
- In Classification Models we have covered the usage of Decision tree Algorithm and its application in-details. If you missed out to check out it please [Click Here](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/4-Classification%20Models/Decision%20Trees#decision-tree-classification) to proceed with Decision tree for Classification. 
- Decision tree builds **Classification** or **Regression models** in the form of a tree structure. It breaks down a data-set into smaller subsets while at the same time an associated decision tree is incrementally developed.
- D-Tree is one of the predictive modeling approaches used in **statistics**, **data mining** and **machine learning**.
- The resulting **D-Tree** contains 3 parts **Root Node**, **Decision Nodes** and **Leaf Nodes**. 
- A **Decision Node** has two or more branches which holds attributes(IV's) where else a **Leaf Node** represents a classification or decision(DV).
- **Root Node** is considered to be the Best predictor which placed as topmost node in tree.
- Decision Tree algorithm belongs to the family of supervised learning algorithms. Unlike other supervised learning algorithms, decision tree algorithm can be used for solving **Regression** and **Classification** problems.
- ***Classification Tree*** are the Tree models where the target variable can take a discrete set of values, in these tree structures, leaves represent class labels and branches represent conjunctions of features that lead to those class labels.
- ***Regression Tree*** Decision trees where the target variable can take continuous values (typically real numbers).
- Some techniques, often called ensemble methods will construct more than one decision tree as follows:
	1. ***AdaBoost***:
		- This method is a subset of **Boosted Tree** algorithms.
		- Incrementally building an ensemble by training each new instance to emphasize the training instances previously mis-modeled.
		- This can be used for regression-type and classification-type problems.
	2. ***Random Forest***:
		- This is also known as **Bagged Decision Tree** or **Bootstrap Aggregated Tree**.
		- This is one of the early ensemble method, builds multiple decision trees by repeatedly resampling training data with replacement, and voting the trees for a consensus prediction.
	3. ***PCA - Principal Component Analysis***:
		-  This is also known as **Rotation Tree**.
		-  Every decision tree is trained by first applying principal component analysis (PCA) on a random subset of the input features.
- ***Decision List*** is one special type of decision tree algorithm available which is a one-sided decision tree, so that every internal node has exactly 1 leaf node and exactly 1 internal node as a child (except for the bottom-most node, whose only child is a single leaf node).

### 2. Types of Decision Tree Algorithm:
- As we know D-Trees can be applied for both Regression and Classification problems, The below summary shows how to identify each category of D-Tree algorithm. We are considering most commonly used Algorithm (ID3) for Regression problem.
- There are several algorithms available in D-Trees as follows
	1. **ID3** - Iterative Dichotomiser 3
	2. **C4.5 (or) J4.8** - successor of ID3
	3. **CART** - Classification And Regression Tree
	4. **CHAID** - Chi-square automatic interaction detection
	5. **MARS** - extends decision trees to handle numerical data better
	6. **Conditional Inference Trees**: Statistics-based approach that uses non-parametric tests as splitting criteria, corrected for multiple testing to avoid overfitting. This approach results in unbiased predictor selection and does not require pruning.
- We are going to see the following most widely used Algorithms in real-world era to solve regression problems.
	1. [ID3](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Decision%20Trees/ReadMe-SDR.md#id3---iterative-dichotomiser-3)

### 3. Metrics Behind D-Trees:
- Algorithms for constructing decision trees usually work top-down, by choosing a variable at each step that best splits the set of items.
- Different algorithms use different metrics for measuring "best" such as ***Gini Index(Gini Impurity)***, ***Information Gain*** and ***Gain Ratio*** and ***Entropy*** and ***SDR - Standard Deviation Reduction***(For Regression Problems).
- ***Gini Index (Gini Impurity)***:

<p align="center">
  <img width="456" height="465" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/CART%20-%20Gini%20Index.JPG?raw=true">
</p>         

- ***Gain Ratio***   

<p align="center">
  <img width="500" height="460" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/C4.5-Gain%20Ratio.JPG?raw=true">
</p>   

   
- ***Information Gain***      

<p align="center">
  <img width="1361" height="313" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/ID3-Information%20Gain.JPG?raw=true">
</p>   
<p align="center">
	<b> Ref: https://en.wikipedia.org/wiki/ID3_algorithm </b>
</p>

- ***Entropy***   

<p align="center">
  <img width="1374" height="281" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/ID3-Entropy.JPG?raw=true">
</p>
<p align="center">
	<b> Ref: https://en.wikipedia.org/wiki/ID3_algorithm </b>
</p>

- ***Standard Deviation Reduction***

<p align="center">
  <img width="350" height="75" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Decision%20Trees/References/FORMULA-SDR.JPG?raw=true">
</p>

- ***Standard Deviation***

<p align="center">
  <img width="205" height="104" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Decision%20Trees/References/FORMULA-SD.JPG?raw=true">
</p>

### 4. Advantages:
- **Simple to understand and interpret** than other Machine Learning Algorithms
- **Able to handle both numerical and categorical data** using Algorithms such as C4.5 and CART and etc...
- Other ML algorithms requires a lot of data preparation where else **D-Tree** requires **Requires little data preparation**.
- D-Trees using **Uses a white box model**.
- D-Trees are used in the field of **Approximate Computing** to produce error tolerance result.


### 5. Over-Fitting:
- Overfitting is one of the problem we will encounter in most of the machine learning models is a significant practical difficulty for D-Trees and other predictive algorithms.
- In simple, "Overfitting is a modeling error which occurs when a function is too closely fit to a limited set of data points".
- In statistics, "The production of an analysis that corresponds too closely or exactly to a particular set of data, and may therefore fail to fit additional data or predict future observations reliably".
- We also seen [Bias-Variance](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/3-Regression%20Models/Polynomial%20Regression#2-bias-variance-trade-off) trade-off in ***Polynomial Regression***
- Concepts like ***Pre-Pruning*** and ***Post-Pruning*** will help us to avoid overfitting in building decision trees.
- **Pre-Pruning**:
	- Stop growing the tree earlier, before it perfectly classifies the training set.
- **Post-Pruning**:
	- Allows the tree to perfectly classify the training set, and then post prune the tree.
	- Practically This approach gives us better result compare to Pre-Pruning, because it is not easy to precisely estimate when to stop growing the tree. 
- To See More about Pruning, Please visit click the link. [How to Handle Overfitting in D-Trees](http://www.saedsayad.com/decision_tree_overfitting.htm)