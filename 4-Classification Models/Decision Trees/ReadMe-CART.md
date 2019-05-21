# CART - Classification And Regression Tree

### Points To Remember:
  - CART - Classification and Regression Tree
  - Gini index
  - Weighted Gini Index
  - D-Tree
  - Attribute - IV
  - Target Variable - DV

### 1. Introduction:
- As we already know, A decision tree is a largely used non-parametric effective machine learning modeling technique for regression and classification problems. To find solutions a decision tree makes sequ
- ential, hierarchical decision about the outcomes variable based on the predictor data.
- In this Module we are going to see about one of the popular and most commonly used decision tree algorithm **CART - Classification and Regression Tree** it is introduced by ***Leo Breiman***.
- CART is an alternative decision tree building algorithm. It can handle both classification and regression tasks.
- This algorithm uses a new metric named gini index to create decision points for classification tasks. We will mention a step by step CART decision tree example by hand from scratch.
- The CART algorithm provides a foundation for important algorithms like bagged decision trees, random forest and boosted decision trees.


#### 1.1 Gini Index:
- A decision tree is built top-down from a root node and involves partitioning the data into subsets that contain instances with similar values (homogeneous).
- CART uses ***Gini Index*** to calculate the homogeneity of a sample.
- If the sample is completely homogeneous the Gini Index is zero.
- Find the formula for Gini Index below.

<p align="center">
  <img width="456" height="465" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/CART%20-%20Gini%20Index.JPG?raw=true">
</p>   

### 2. FlowChat:
- Please find the below flowchart which explains the pseudo-code of CART Algorithm.

<p align="center">
  <img width="650" height="500" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/CART%20-%20Flow%20chat.JPG?raw=true">
</p>   


### 3. CART Step by Step Implementation:
- Now we are going to see how to implement D-Tree using CART Algorithm. for the step-by-step implementation we are going to consider the same **Play-Tennis** data-set used in ID3. Please find the below data-set for your reference.

<p align="center">
  <img width="500" height="500" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/CART-Input%20Dataset.JPG?raw=true">
</p>   

- It has 4 IV's and 1 DV which is Categorical in nature, the problem we are trying to solve here is based on the IV categorical in nature we are going to predict Output target class(DV) using CART Algorithm.
- As we all now CART is best suitable for handling Input/Output variable Categorical in nature so we are going to use this here.  

- Finding the Gini Index/Weighted Gini Index of each attribute as same as above mentioned formula and you will end-up with Gini index values for each input attribute as shown below.

<p align="center">
  <img width="750" height="500" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/CART%20-%20Gini%20Cal%20-%201.JPG?raw=true">
</p>    

<p align="center">
  <img width="750" height="500" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/CART%20-%20Gini%20Cal%20-%202.JPG?raw=true">
</p>    

<p align="center">
  <img width="750" height="500" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/CART%20-%20Gini%20Cal%20-%203.JPG?raw=true">
</p>    

<p align="center">
  <img width="750" height="500" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/CART%20-%20Gini%20Cal%20-%204.JPG?raw=true">
</p>    

- If you see Attribute ***Outlook*** has the lowest Gini Index. so we are going to consider that as root element and and build our tree like this.

<p align="center">
  <img width="826" height="210" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/ID3-T1.PNG?raw=true">
</p>   

- Now divide the data-set into sub-Branches(Sub Partitions) and check any branch met below conditions. If any branch met our condition then consider that as ***Leaf Node***
	- Every element in the subset belongs to the same class and there is no further split possible, in which case the node is turned into a leaf node and labeled with the class of the examples.

<p align="center">
  <img width="774" height="516" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/ID3-SGS.PNG?raw=true">
</p>   

<p align="center">
  <img width="745" height="185" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/ID3-T2.PNG?raw=true">
</p>   

- Perform **Step-2** for remaining sub-branch and continue the iteration until the below case will occur.
	- **EOT-End Of Tree**: There are no more attributes to be selected, but the examples still do not belong to the same class. In this case, the node is made a leaf node and labeled with the most common class of the examples in the subset.
- Once we finished the above all steps will see Tree like below.

<p align="center">
  <img width="924" height="507" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/ID3-T3.PNG?raw=true">
</p>   

### 4. CART using Python
- [How to Write your first program using python]()
- If you completed the above steps you can see the D-Tree Algorithm predicts test samples based on training result.
- There something we have to look in when we are working with D-Trees and one of'em is ***Overfitting***. Please see more about how to avoid Over-fitting in CART [click link](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/4-Classification%20Models/Decision%20Trees#5-over-fitting).


### 5. Additional Use-cases:


##### Reference URL: