# C-4.5 (Improved Version of ID3)

### Points To Remember:
  - ID3 - Iterative Dichotomizer
  - Entropy
  - Information Gain
  - Split Info
  - Gain Ratio
  - D-Tree

### 1. Introduction:
- C4.5 Algorithm is one of the most popular algorithm used to solve classification problems after ID3. Where ID3 Algorithms is mainly used to predict Input/Output attributes Categorical in nature. The C4.5 is more improved version of ID3 which will predict Input/Output attributes Categorical/Continues in nature.
- The core algorithm for building decision trees called ID3 by **J. R. Quinlan** which employs a top-down, greedy search through the space of possible branches with no backtracking.
- As like ID3 here we are using ***Entropy***, ***Information Gain***, ***Split Info*** and ***Gain Ratio*** to construct a decision tree.
- How C4.5 Works:
	- The C4.5 algorithm begins with the original set **S** as the root node. On each iteration of the algorithm, it iterates through every unused attribute of the set **S** and calculates the Entropy (or Gain Ratio) of that attribute.
	- It then selects the attribute which has the smallest entropy (or largest Gain Ratio) value.
	- The **Root Node** Selection also follows the same process.
	- The set **S** is then split or divided by the selected attribute to produce subsets of the data.
	- C4.5 continues to **recur** on each subset, considering only attributes that never selected before.
		- Every element in the subset belongs to the same class and there is no further split possible, in which case the node is turned into a leaf node and labeled with the class of the examples.
		- **EOT-End Of Tree**: There are no more attributes to be selected, but the examples still do not belong to the same class. In this case, the node is made a leaf node and labeled with the most common class of the examples in the subset.

#### 1.1 Entropy:
- A decision tree is built top-down from a root node and involves partitioning the data into subsets that contain instances with similar values (homogeneous).
- ID3 algorithm uses entropy to calculate the homogeneity of a sample.
- If the sample is completely homogeneous the entropy is zero
- If the sample is an equally divided it has entropy of one.
- To build a decision tree, we need to calculate two types of entropy:
  - Find Entropy of Target Variable
  - Find Entropy of Input Attribute
- Find the formula for Entropy below.
<p align="center">
  <img width="1374" height="281" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/ID3-Entropy.JPG?raw=true">
</p>
<p align="center">
	<b> Ref: https://en.wikipedia.org/wiki/ID3_algorithm </b>
</p>

#### 1.2 Information Gain:
- The information gain is based on the decrease in entropy after a data-set is split on an attribute.
- Constructing a decision tree is all about finding attribute that returns the highest information gain.
- Steps to Find Information Gain:
  1. Calculate entropy of the target variable
  2. The data-set is then split on the different attributes. The entropy for each branch is calculated.
  3. Then it is added proportionally, to get total entropy for the split. The resulting entropy is subtracted from the entropy before the split. 
  4. The result is the Information Gain, or decrease in entropy. 
- Find the formula for Information Gain below.
<p align="center">
  <img width="1361" height="313" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/ID3-Information%20Gain.JPG?raw=true">
</p>
<p align="center">
	<b> Ref: https://en.wikipedia.org/wiki/ID3_algorithm </b>
</p>

### 1.3 Information Gain Ratio:
- As we discussed earlier in C4.5 Algorithm we are using gain ratio instead Information gain to find the optimal nodes.
- In order to find Gain Ratio we need to find ***Entropy***, ***Information Gain*** and ***Split Info*** first. and the below formula will show your how to derive gain ration for input attributes.

<p align="center">
  <img width="500" height="460" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/C4.5-Gain%20Ratio.JPG?raw=true">
</p>   


### 2. Flow Chart:
- Please find the below flow chat which explains the pseudocode of C4.5 Algorithm.

<p align="center">
  <img width="750" height="630" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/C4.5-FlowChat.JPG?raw=true">
</p>   

### 3. C4.5 Step by Step Implementation:
- Now we are going to see how to implement D-Tree using C4.5 Algorithm. for the step-by-step implementation we are going to consider the famous **Play-Tennis** data-set with some of the attributes continues in nature. Please find the below data-set for your reference.

<p align="center">
  <img width="578" height="633" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/C4.5-Dataset.JPG?raw=true">
</p>  

- It has 4 IV's and 1 DV which is Categorical/Continues in nature, the problem we are trying to solve here is based on the IV categorical/continues in nature we are going to predict Output target class(DV) using ID3 Algorithm.
- As we all now C4.5 is best suitable for handling Input/Output variable Categorical in nature so we are going to use this here. 

**Step-1:** ***Find Entropy of Target Variable***
- Finding the entropy of the **System(target variable)** is important since it is part of Finding information gain and Gain Ratio for each attribute. so we are going to find entropy of the System first. And to do that use the Entropy formula mentioned above and apply it on the **System(target variable)**.
- Please find the below image for reference. You will end up with entropy value of **0.94**.

<p align="center">
  <img width="853" height="608" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/C4.5-Entropy-DV.JPG?raw=true">
</p>   

**Step-2:** ***Find Gain Ratio of Each Attribute(IV's)***
- Finding the Gain Ratio of each input attribute will help us to identify the root element.
- As we seen above finding Gain ratio involves finding ***Entropy***, ***Information Gain*** and ***Split Info***.
- Please find the below images to find Gain Ratio for categorical attributes(Outlook and Windy).

**Outlook**
<p align="center">
  <img width="1242" height="622" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/C4.5-GR-1.JPG?raw=true">
</p>   

**Windy**
<p align="center">
  <img width="999" height="613" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/C4.5-GR-2.JPG?raw=true">
</p>   

- Finding Gain Ratio for continues attributes is slightly different than categorical variables, why because here each and every row is unique and we have to repeat the steps for each row until we get the maximum Gain Ratio for each value in attribute.
- Please find the below images to find Gain Ratio for continues attributes

**Temp**
<p align="center">
  <img width="1263" height="558" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/C4.5-GR-3_1.JPG?raw=true">
</p>   

<p align="center">
  <img width="1303" height="525" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/C4.5-GR-3_2.JPG?raw=true">
</p>   

**Humidity**
<p align="center">
  <img width="1458" height="566" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/C4.5-GR-4_1.JPG?raw=true">
</p>   

<p align="center">
  <img width="1212" height="461" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/C4.5-GR-4_2.JPG?raw=true">
</p>   

- If you see Attribute ***Outlook*** has the Highest Information Gain. so we are going to consider that as root element and and build our tree like this.

<p align="center">
  <img width="826" height="210" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/ID3-T1.PNG?raw=true">
</p>   

- Now divide the data-set into sub-Branches(Sub Partitions) and check any branch met below conditions. If any branch met our condition then consider that as ***Leaf Node***
	- Every element in the subset belongs to the same class and there is no further split possible, in which case the node is turned into a leaf node and labeled with the class of the examples.
<p align="center">
  <img width="1302" height="845" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/C4.5-SB.JPG?raw=true">
</p>   

<p align="center">
  <img width="745" height="185" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/ID3-T2.PNG?raw=true">
</p> 

- Perform **Step-2** for remaining sub-branch and continue the iteration until the below case will occur.
	- **EOT-End Of Tree**: There are no more attributes to be selected, but the examples still do not belong to the same class. In this case, the node is made a leaf node and labeled with the most common class of the examples in the subset.
- Once we finished the above all steps will see Tree like below.

<p align="center">
  <img width="1526" height="832" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/References/C4.5-FinalTree.JPG?raw=true">
</p>   

### 4. C4.5 using Python
- [How to Write your first program using python]()
- If you completed the above steps you can see the D-Tree Algorithm predicts test samples based on training result.
- There something we have to look in when we are working with D-Trees and one of'em is ***Overfitting***. Please see more about how to avoid Over-fitting in C4.5 [click link](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/4-Classification%20Models/Decision%20Trees#5-over-fitting).

### 5. Additional Use-cases:

##### Reference URL:
[To get Initial flavor of C4.5](https://en.wikipedia.org/wiki/C4.5_algorithm)   
[To get Understanding of C4.5](https://sefiks.com/2018/05/13/a-step-by-step-c4-5-decision-tree-example/)