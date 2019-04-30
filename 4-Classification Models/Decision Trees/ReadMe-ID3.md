# ID3 - Iterative Dichotomizer 3

### Points To Remember:
  - ID3 - Iterative Dichotomizer
  - Entropy
  - Information Gain
  - D-Tree
  - Attribute - IV
  - Target Variable - DV
  
### 1. Introduction:
- ID3[Iterative Dichotomizer] Algorithm is one of the most popular algorithm used to solve classification problems. ID3 Algorithms is mainly used to predict Input/Output variables Categorical in nautre.
- The core algorithm for building decision trees called ID3 by **J. R. Quinlan** which employs a top-down, greedy search through the space of possible branches with no backtracking.
- It uses ***Entropy*** and ***Information Gain*** to construct a decision tree.
- ID3 is the precursor to the C4.5 algorithm, and is typically used in the machine learning and natural language processing domains.
- How ID3 Works:
  - The ID3 algorithm begins with the original set **S** as the root node. On each iteration of the algorithm, it iterates through every unused attribute of the set **S** and calculates the entropy (or information gain) of that attribute.
  - It then selects the attribute which has the smallest entropy (or largest information gain) value.
  - The **Root Node** Selection also follows the same process.
  - The set **S** is then split or divided by the selected attribute to produce subsets of the data.
  - ID3 continues to **recur** on each subset, considering only attributes that never selected before.
  - ID3 will **stop recursion** on any one of the following criteria:
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
  <img width="1374" height="281" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/DTrees/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/4-Classification%20Models/Decision%20Trees/References/ID3-Entropy.JPG?raw=true">
</p>
<p align="center">
	<b> Ref: https://en.wikipedia.org/wiki/ID3_algorithm </b>
</p>

#### 1.2 Information Gain:
- The information gain is based on the decrease in entropy after a dataset is split on an attribute.
- Constructing a decision tree is all about finding attribute that returns the highest information gain.
- Steps to Find Information Gain:
  1. Calculate entropy of the target variable
  2. The dataset is then split on the different attributes. The entropy for each branch is calculated.
  3. Then it is added proportionally, to get total entropy for the split. The resulting entropy is subtracted from the entropy before the split. 
  4. The result is the Information Gain, or decrease in entropy. 
- Find the formula for Information Gain below.
<p align="center">
  <img width="1361" height="313" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/DTrees/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/4-Classification%20Models/Decision%20Trees/References/ID3-Information%20Gain.JPG?raw=true">
</p>
<p align="center">
	<b> Ref: https://en.wikipedia.org/wiki/ID3_algorithm </b>
</p>
  
### 2. FlowChat:
- Please find the below flowchat which explains the pseudocode of ID3 Algorithm. The below chat will illustrate the psuedocode of ID3 Algorithm.
<p align="center">
  <img width="449" height="523" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/DTrees/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/4-Classification%20Models/Decision%20Trees/References/ID3-Pseudo.PNG?raw=true">
</p>

### 3. ID3 Step by Step Implementation:
- Now we are going to see how to implement D-Tree using ID3 Algoritm. for the step-by-step implementation we are going to consider the famous **Play-Tennis** dataset. Please find the below dataset for your reference.

<p align="center">
  <img width="743" height="459" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/DTrees/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/4-Classification%20Models/Decision%20Trees/References/ID3-ICT-Dataset.PNG?raw=true">
</p>   

- It has 4 IV's and 1 DV which is Categorical in nature, the problem we are trying to solve here is based on the IV categorical in nature we are going to predict Output target class(DV) using ID3 Algorithm.
- As we all now ID is best suitable for handling Input/Output variable Categorical in nature so we are going to use this here.  

**Step-1:** ***Find Entropy of Target Variable***   
- Finding the entropy of the **System(target variable)** is important since it is part of Finding information gain for each attribute. so we are going to find entropy of the System first. And to do that use the Entropy formula mentioned above and apply it on the **System(target variable)**.
- Please find the below image for reference. You will endup with entropy value of **0.94**. 

<p align="center">
  <img width="673" height="486" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/DTrees/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/4-Classification%20Models/Decision%20Trees/References/ID3-ETV.PNG?raw=true">
</p>
	
**Step-2:** ***Find Entropy of Each Attribute(IV's)***   
- Finding the entropy of each attribute as same as above step and you will endup with entropy values for each input attribute as shown below. 

<p align="center">
  <img width="866" height="450" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/DTrees/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/4-Classification%20Models/Decision%20Trees/References/ID3-EA.PNG?raw=true">
</p>   

- **Note:** we know to choose root attribute neither Entropy has to low nor Information gain has to be large even if you get small value among the attributes we should not go to conclusion, we have to find information gain for each attribute.
	
**Step-3:** ***Find Information Gain for Each Attribute(IV's)***   
- To find **Information Gain** use the above mentioned formula, which will show below results.

<p align="center">
  <img width="492" height="441" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/DTrees/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/4-Classification%20Models/Decision%20Trees/References/ID3-IG.PNG?raw=true">
</p>   

- If you see Attribute ***Outlook*** has the Highest Information Gain. so we are going to consider that as root element and and build our tree like this.

<p align="center">
  <img width="826" height="210" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/DTrees/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/4-Classification%20Models/Decision%20Trees/References/ID3-T1.PNG?raw=true">
</p>   

- Now divide the data-set into sub-Branches(Sub Partitions) and check any brach met below conditions. If any branch met our condition then consider that as ***Leaf Node***
	- Every element in the subset belongs to the same class and there is no further split possible, in which case the node is turned into a leaf node and labeled with the class of the examples.

<p align="center">
  <img width="774" height="516" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/DTrees/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/4-Classification%20Models/Decision%20Trees/References/ID3-SGS.PNG?raw=true">
</p>   

<p align="center">
  <img width="745" height="185" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/DTrees/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/4-Classification%20Models/Decision%20Trees/References/ID3-T2.PNG?raw=true">
</p>   

- Perform **Step-2** for remaining sub-branch and continue the iteration untill the below case will occur.
	- **EOT-End Of Tree**: There are no more attributes to be selected, but the examples still do not belong to the same class. In this case, the node is made a leaf node and labeled with the most common class of the examples in the subset.
- Once we finished the above all steps will see Tree like below.

<p align="center">
  <img width="924" height="507" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/DTrees/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/4-Classification%20Models/Decision%20Trees/References/ID3-T3.PNG?raw=true">
</p>   

### 4. ID3 using Python
- [How to Write your first program using python](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/DTrees/Python%20%2B%20Machine%20Learning%20%2B%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/4-Classification%20Models/Decision%20Trees/How%20to%20write%20in%20Python%20-%20ID3.md#how-to-write-in-python---id3)
- If you completed the above steps you can see the D-Tree Algorithm predicts test samples based on training result.
- There something we have to look in when we are working with D-Trees and one of'em is ***Overfitting***. Please see more about how to avoid Overfitting in ID3 [click link](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/DTrees/Python%20+%20Machine%20Learning%20+%20Deep%20Learning/Machine%20Learning%20The%20Complete%20Reference/4-Classification%20Models/Decision%20Trees#5-over-fitting).

### 5. Additional Usecases:


##### Reference URL:
[To get Initial flavour of ID3](http://www.saedsayad.com/decision_tree.htm)   
[To get Understanding of ID3](https://en.wikipedia.org/wiki/ID3_algorithm)
