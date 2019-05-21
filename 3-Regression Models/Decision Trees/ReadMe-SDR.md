# ID3 - Iterative Dichotomiser 3

### Points To Remember:
  - D-Tree
  - Attribute - IV
  - Target Variable - DV
  - SD = Standard Deviation
  - SDR = Standard Deviation Reduction
  - ID3 = Iterative Dichotomiser 3


### 1. Introduction:
- ID3[Iterative Dichotomizer 3] Algorithm is one of the most popular algorithm used to solve classification problems.  ID3 Algorithms is mainly used to predict Input/Output variables Categorical in nature.
- The core algorithm for building decision trees called ID3 by **J. R. Quinlan** which employs a top-down, greedy search through the space of possible branches with no backtracking.
- The ID3 algorithm can be used to construct a decision tree for ***regression*** by replacing ***Information Gain*** with ***Standard Deviation Reduction***.

***SDR Formula***
<p align="center">
  <img width="325" height="75" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Decision%20Trees/References/FORMULA-SDR.JPG?raw=true">
</p>   

***SD Formula***
<p align="center">
  <img width="205" height="104" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Decision%20Trees/References/FORMULA-SD.JPG?raw=true">
</p>   


### 2. Flow Chat:
- Please find the below flowchart which explains the pseudocode of ID3 Algorithm for Regression problem.

<p align="center">
  <img width="1562" height="861" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Decision%20Trees/References/REG-FlowChat.JPG?raw=true">
</p>   


### 3. ID3 Step by Step Implementation:
- Now we are going to see how to implement D-Tree using ID3 Algorithm. For the step-by-step implementation we are going to consider the famous Play-Tennis data-set where the Target Variable is the Real Numbers. Please find the below data-set for your reference.

<p align="center">
  <img width="705" height="622" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Decision%20Trees/References/DataSet.JPG?raw=true">
</p>   

- It has 4 IV's which is categorical in nature and 1 DV which is Continues in nature, The problem we are trying to solve here is based on the IV categorical in nature we are going to predict Output target class(DV) using SDR Algorithm.

**Step - 1:** ***Find SD of Target Variable***
- Finding the SD of the System(target variable) is important since it is part of SDR gain for each attribute. so we are going to find SD of the System first. And to do that use the SD formula mentioned above and apply it on the System(target variable). 
- Please find the below image for reference. You will end-up with entropy value of **9.32**.

<p align="center">
  <img width="1282" height="712" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Decision%20Trees/References/REG-DV-SD.JPG?raw=true">
</p>   

**Step - 2:** ***Find SD of Input Attribute(IV)***
- Finding the SD of each attribute as same as above step and you will end-up with SD values for each input attribute as shown below.

<p align="center">
  <img width="1431" height="841" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Decision%20Trees/References/REG-IV-SD.JPG?raw=true">
</p>   

**Step - 3:** ***Find SDR of Input Attribute(IV)***
- To find SDR use the above mentioned formula, which will show below results.

<p align="center">
  <img width="770" height="657" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Decision%20Trees/References/REG-IV-SDR.JPG?raw=true">
</p>   

- If you see Attribute ***Outlook*** has the Highest SDR. So we are going to consider that as root element and and build our tree like this.

<p align="center">
  <img width="826" height="210" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Decision%20Trees/References/DTree-T1.JPG?raw=true">
</p>   

- Now divide the data-set into sub-Branches(Sub Partitions) and check any branch met below conditions. If any branch met our condition then consider that as Leaf Node.
- In practice, we need some termination criteria. For example, when ***coefficient of deviation (CV)*** for a branch becomes smaller than a certain ***threshold*** (e.g., 10%).

<p align="center">
  <img width="774" height="516" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Decision%20Trees/References/DTree-SB.JPG?raw=true">
</p>   

- Lets assume the threshold for our problem to be 10% and calculate the ***coefficient of variation*** for sub-branches
- **coefficient of variation (CV)**:
	- The coefficient of variation (CV) is a measure of relative variability. It is the ratio of the standard deviation to the mean (average).
	- It is also known as relative standard deviation (RSD), is a standardized measure of dispersion of a probability distribution or frequency distribution.
	- Formula for ***coefficient of deviation (CV)***:
<p align="center">
  <img width="320" height="100" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Decision%20Trees/References/ID3-CV.jpg?raw=true">
</p>   

- If we apply above formula on attribute Outlook sub-branches we will get the following results. which clearly shows **Overcast** has the lowest CV value of (8%) which is smaller than Threshold value (10%). If a CV value is smaller than Threshold value means low in variance so we can consider that as Leaf Node.
- And the above tree will look like this.

<p align="center">
  <img width="774" height="516" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Decision%20Trees/References/DTree-T2.JPG?raw=true">
</p>   

- Perform same step for remaining sub-branch and continue the iteration until will find values for all the sub-branches.
- Once we finished the above all steps will see Tree like below.

<p align="center">
  <img width="924" height="507" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Decision%20Trees/References/DTree-FinalTree.JPG?raw=true">
</p>   


### 4. SDR Using Python
- [How to Write your first program using python](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/3-Regression%20Models/Decision%20Trees/Decision%20Tree%20Regression%20in%20Python.md#decision-tree-regression-in-python)
- If you completed the above steps you can see the D-Tree Algorithm predicts test samples based on training result.
- Since ID3 for Regression not give much accuracy it will be used only on Approximate Computing and not much in Regression.