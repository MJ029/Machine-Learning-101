# RANDOM FOREST CLASSIFICATION

#### Things to Remember:
- D-Trees
- Random Forest
- Bagging
- CART 
- randomized node optimization
- Overfitting
	
### 1. Introduction:
- Hi All, Welcome to the 6'th and final part of Classification models which is famously known as ***Random Forest Classification*** which is invented by **Tin Kam Ho** in the year of 1995 using random subspace method.
- Random Forest / Random Decision Forest is the part of ensemble learning method for classification, regression. Random Forest operates by constructing a multitude of decision trees at training time and outputting the class that is the mode of the classes (classification) or mean prediction (regression) of the individual trees.
- Random Forest does not OverFit, which means it give us the solution for major problem in D-Trees which is known as ***OverFitting*** the Training set.
- **Tin Kam Ho** formulation, is a way to implement the "stochastic discrimination" approach to classification proposed by Eugene Kleinberg. But in 2001 An extension of the algorithm was developed by **Leo Breiman** and **Adele Cutler** and it has been registered as "Random Forests". This paper describes a method of building a forest of uncorrelated trees using a ***CART*** like procedure, combined with ***randomized node optimization & bagging***. Now it's owned by **Minitab Inc**.
- In addition, this paper combines several ingredients as below.
	- Using ***out-of-bag error*** as an estimate of the ***generalization error***.
	- Measuring variable importance through permutation.
- In Simple, Random forest builds multiple decision trees and merges them together to get a more accurate and stable prediction.

### 2. Algorithms and Metrics:
- Decision trees are a popular method for various machine learning tasks. but same way it tend to lead us into Overfitting [i.e. have low bias, but very high variance].
- Random forests are a way of averaging multiple deep decision trees, trained on different parts of the same training set, with the goal of reducing the variance.
- Random Forest adds additional randomness to the model, while growing the trees. Instead of searching for the most important feature while splitting a node, it searches for the best feature among a random subset of features. This results in a wide diversity that generally results in a better model. Therefore, in Random Forest, a random subset of the features is taken into consideration by the algorithm for splitting a node.

**Random Forest Definition from [Book: The Elements of Statistical Learning]**
- For b = 1 to B:
	- Draw a bootstrap sample Z* of size N from the training data.
	- Grow a random-forest tree Tb to the bootstrapped data, by re-cursively repeating the following steps for each terminal node of the tree, until the minimum node size nmin is reached.
		- Select m variables at random from the p variables.
		- Pick the best variable/split-point among the m.
		- Split the node into two daughter nodes.
- Output the ensemble of trees {Tb}B1		

#### 2.1 Bagging (or) Bootstrap aggregating:
- ***Bootstrap aggregating***, also called ***bagging*** is a special case of the model averaging approach. It is a machine learning ensemble meta-algorithm designed to improve the stability and accuracy of machine learning algorithms used in classification and regression problems. 
- It also helps avoid overfitting by reducing the Variance in training set. Eventhough it is widely being used in ***D-Trees*** it can be used with most of the machine learning algorithms
- How Bagging works:
	- Bagging generates new training set D(i) with **M** samples each size of n' from the given training set D of size **n** by sampling from D ***Uniformly with Replacement***.
	- By ***Sampling Uniformly with Replacement***, some Observations may repeat in each D(i).
	- Some **M** samples were missed out during ***Sampling Uniformly with Replacement*** which are known as ***[OOB]Out-Of-Bag records***. Basically these OOB were used to evaluate the model during the testset in Random Forest.
	- We will apply ***bootstrap sample*** on D(i) if n'=n. ***bootstrap sample*** is the method where large n the set D(i) is expected to have the fraction
		[1 - 1/e] ~ (63.2%) of Unique sample of D, the rest being duplicates.
	- Models were fitted using the above m bootstrap samples and predict the output by averaging the output (for regression) or voting (for classification).
	- It helps D-Trees to improve accuracy but in the other hand it can mildly degrade the performance of stable methods such as K-nearest neighbors.
	
#### 2.2 OOB[Out-Of-Bag] Error Estimate:
- In random forests, there is no need for cross-validation or a separate test set to get an unbiased estimate of the test set error. It is estimated internally, during the training run as follows.
	- Each tree is constructed using a different bootstrap sample from the original data. 
	- About one-third of the cases are left out of the bootstrap sample and not used in the construction of the kth tree.
	- Put each case left out in the construction of the kth tree down the kth tree to get a classification.
	- In this way, a test set classification is obtained for each case in about one-third of the trees. 
	
#### 2.3 Missing Value Handling:
- As we all know handling missing value in a data set can be done in 2 ways, These replacement values are called fills.
	- If the Input variable is not categorical, then the method computes the median of all values of this variable. Then it uses this value to replace all missing values of the mth variable.
	- If the input variable is categorical, the replacement is the most frequent non-missing value.
- Random Forest also follows the above 2 steps as (Approcah-1), which give us expected result.
- It has one more way to handle the same situation, eventhough it is computationally more expensive but has given better performance than the above (Approach-1) even with large amounts of missing data.
	- It replaces missing values only in the training set.
	- It begins by doing a rough and inaccurate filling in of the missing values.
	- Then it does a forest run and computes proximities.
		- If x(m,n) is a missing continuous value, estimate its fill as an average over the non-missing values of the mth variables weighted by the proximities between the nth case and the non-missing value case.
		- If it is a missing categorical variable, replace it by the most frequent non-missing value where frequency is weighted by proximity.
	- Now iterate-construct a forest again using these newly filled in values, find new fills and iterate again. Our experience is that 4-6 iterations are enough.
	
#### 2.4 Proximities:
- These are one of the most useful tools in random forests. The proximities originally formed a NxN matrix. After a tree is grown, put all of the data, both training and oob, down the tree.
- If cases k and n are in the same terminal node increase their proximity by one. At the end, normalize the proximities by dividing by the number of trees.
- Users noted that with large data sets, they could not fit an NxN matrix into fast memory. A modification reduced the required memory size to NxT where T is the number of trees in the forest. 
- To speed up the computation-intensive scaling and iterative missing value replacement, the user is given the option of retaining only the nrnn largest proximities to each case.
- When a test set is present, the proximities of each case in the test set with each case in the training set can also be computed. The amount of additional computing is moderate.

### 3. How Random forest is different from D-Trees:
- As all we know Random Forest is a collection of Decision Trees which improves accuracy of the model by reducing the variance, still we have some difference between them as below mentioned areas.

**Model Fitting:**
	- Let us assume we are feeding a input dataset with features and labels into a decision tree during training, it will formulate some set of rules, which will be used to make the predictions.
	- For Example, you have to predict whether a person has Cancer or not. You could collect the attributes from his scan result and some features that describe it nature.
	- If you put the features and labels into a decision tree, it will generate some rules. Then you can predict whether the person has cancer or not.
	- In comparison, the Random Forest algorithm randomly selects observations and features to build several decision trees and then averages the results.

**OverFitting:**
	- Deep decision trees might suffer from overfitting. Random Forest prevents overfitting most of the time, by creating random subsets of the features and building smaller trees using these subsets. 

**Relative Feature Importance:***
	- Another amazing fact of random forest is that it is very easy to measure the relative importance of each feature on the prediction.
	- Sklearn provides a great tool for this, that measures a features importance by looking at how much the tree nodes, which use that feature, reduce impurity across all trees in the forest. 
	- It computes this score automatically for each feature after training and scales the results, so that the sum of all importance is equal to 1.
	- By looking the feature importance we can decice which feature to remove from input training set.
	
### 4. Application Areas:
- Random Forest can be used for wide range of Application ssuch as follows
	- Image Classification
	- Fraudulent Detecting
	- Recommendation engines
	- Feature Selection
	
### 5. Random Forest using Python
- [How to Write your first program using python]()   
- If you completed the above steps you can see the Random Forest Algorithm predicts test samples based on training result.

##### References:
[Random Forest - Intiution](https://www.youtube.com/watch?v=3kYujfDgmNk)   
[Random Forests - Leo Breiman and Adele Cutler](https://www.stat.berkeley.edu/~breiman/RandomForests/cc_home.htm)
