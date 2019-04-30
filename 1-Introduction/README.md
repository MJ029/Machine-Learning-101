# 1.About the Course:
- Hi, a warm Welcome to you. If you are one of the person who is trying to explore more detail in Machine Learning like others, but don't know where/how to start ? Hooray, you are in the right place at right time.
- The course has been designed by a Professional Machine Learning Engineer, who is trying to create more opportunists in Machine Learning by sharing his knowledge and helping you to solve complex Algorithms in simple way.
- I am going to take you step by step to the world of Machine Learning, With every tutorial in this course you will develop new skills and improve your understanding in Machine Learning.
- Moreover, the course is packed with practical exercises which are based on real-life examples. So you will learn the theory and also get some hands-on practice by building your own models and use-cases.
- The course is structured the following way:
	1. [Data Pre-Processing](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/2-Data%20Pre-Processing#data-Pre-processing)
		1. [Handling Missing Data](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/2-Data%20Pre-Processing#1-handling-missing-data)
		2. [Handling Categorical Data](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/2-Data%20Pre-Processing#2-handling-categorical-data)
		3. [Splitting Data-Set into Dev/Training/Test set](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/2-Data%20Pre-Processing#3-spiting-your-data-set-into-devtrainingtest-set)
		4. [Feature Scaling](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/2-Data%20Pre-Processing#4-feature-scaling)    
	2. [Regression Models](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/3-Regression%20Models#regression-models)
		1. [Simple Linear Regression](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/3-Regression%20Models/Simple%20Linear%20Regression#simple-linear-regression)
		2. [Multiple Linear Regression](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/3-Regression%20Models/Multi%20Linear%20Regression#multi-linear-regression)
		3. [Polynomial Regression](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/3-Regression%20Models/Polynomial%20Regression#polynomial-regression)
		4. [SVR - Support Vector Regression](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/3-Regression%20Models/Support%20Vector%20Machine/ReadMe.md#svr---support-vector-regression)
		5. [Decision Tree Regression](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/3-Regression%20Models/Decision%20Trees#decision-tree-regression)
		6. Random Forest Regression
		7. Evaluating Model Performance
	3. Classification 
		 1. Logistic Regression
		 2. K-NN
		 3. [SVM - Support Vector Machine](https://github.com/ManikandanJeyabal/Machine-Learning-101/tree/master/4-Classification%20Models/SVM#support-vector-machine)
		 4. Naive Bayes
		 5. [Decision Tree Classification](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/ReadMe.md#decision-tree-classification)
			 1. [ID3](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/ReadMe-ID3.md#id3---iterative-dichotomizer-3)
			 2. [C4.5 or J4.8](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/ReadMe-C45.md#c-45-improved-version-of-id3)
			 3. [CART](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/4-Classification%20Models/Decision%20Trees/ReadMe-CART.md#cart---classification-and-regression-tree)
		 6. Random Forest Classification
	4. Clustering
		 1. K-Means
		 2. Hierarchical Clustering
	5. Association Rule Learning 
		 1. Apriori Rule
		 2. Eclat Rule
	6. Reinforcement Learning
		1. UCB - Upper Confidence Bound
		2. Thompson Sampling
	7. Deep Learning
		1. Artificial Neural Networks
		2. Convolutional Neural Networks
	8. Dimensionality Reduction 
		1. PCA
		2. LDA
	9. Model Selection & Boosting
		1. k-fold Cross Validation
		2. Parameter Tuning
		3. Grid Search
		4. XGBoost
  
# 2.Targeted Audience:
- Anyone interested in Machine Learning.
- Any data analysts who want to level up in Machine Learning.
- Students who have at least high school knowledge in math and who want to start learning Machine Learning.
- Any intermediate level people who know the basics of machine learning, including the classical algorithms like linear regression or logistic regression, but who want to learn more about it and explore all the different fields of Machine Learning.
- Any people who are not that comfortable with coding but who are interested in Machine Learning and want to apply it easily on datasets.
- Any people who are not satisfied with their job and who want to do something new in Machine Learning.

# 3.What you will Learn:
- Master Machine Learning on Python.
- Have a great intuition of many Machine Learning models.
- Make accurate predictions by powerful analysis methods.
- Make robust Machine Learning models.
- Handle specific topics like Reinforcement Learning, NLP and Deep Learning and Handle advanced techniques like Dimensionality Reduction
# 4.What is Machine Learning:
- **Machine learning** is a method of data analysis that automates analytical model building. 
- It is a branch of artificial intelligence based on the idea that systems can learn from data, find patterns and make decisions with minimal human intervention. 
- While artificial intelligence (AI) is the broad science of mimicking human abilities, machine learning is a specific subset of AI that trains a machine how to learn.
- The processes involved in machine learning are similar to data mining and predictive modeling. Both require searching through data to look for patterns and adjusting program actions accordingly.
- Many people are familiar with machine learning from shopping on the internet and being served ads related to their purchase. This happens because recommendation engines use machine learning to personalize online ad delivery in almost real-time.
- Machine learning algorithms are often categorized as **Supervised** or **Unsupervised** or **Semi-Supervised** Learning.

#### 4.1 Supervised Learning:
- Supervised algorithms require a data scientist or data analyst with machine learning skills to provide both input and desired output, in addition to furnishing feedback about the accuracy of predictions during algorithm training.
- Data scientists determine which variables, or features, the model should analyze and use to develop predictions.
- Once training is complete, the algorithm will apply what was learned to new data.
- In simple terms Supervised Learning is know as "Supervised learning is so named because the data scientist acts as a guide to teach the algorithm what conclusions it should come up with". and it is the more commonly used between the three.
- It includes such algorithms as linear and logistic regression, multi-class classification, and support vector machines and etc... **For Example:** A child might learn arithmetic from a teacher
- Supervised learning requires that the algorithm’s possible outputs are already known and that the data used to train the algorithm is already labeled with correct answers.
- **For Example:** Classification algorithm will learn to identify animals after being trained on a dataset of images that are properly labeled with the species of the animal and some identifying characteristics

#### 4.2 Unsupervised Learning:
- Unsupervised algorithms do not need to be trained with desired outcome data. Instead, they use an iterative approach called deep learning to review data and arrive at conclusions. 
- Unsupervised learning algorithms also uses an area called neural networks, they used for more complex processing tasks than supervised learning systems, including image recognition, speech-to-text and natural language generation.
- These neural networks work by combing through millions of examples of training data and automatically identifying often subtle correlations between many variables. Once trained, the algorithm can use its bank of associations to interpret new data.
- These algorithms have only become feasible in the age of big data, as they require massive amounts of training data.
- Some examples of unsupervised machine learning algorithms include k-means clustering, principal and independent component analysis, and association rules.

#### 4.3 Which algorithm to choose for my problem:
- Choosing to use either a supervised or unsupervised machine learning algorithm typically depends on factors related to the structure and volume of your data and the use case of the issue at hand.
- A well-rounded data science program will use both types of algorithms to build predictive data models that help stakeholders make decisions across a variety of business challenges.

#### 4.4 Semi-Supervised Learning:
- Semi-supervised learning is a class of machine learning tasks and techniques that also make use of unlabeled data for training – typically a small amount of labeled data with a large amount of unlabeled data.
- Semi-supervised learning falls between unsupervised learning (without any labeled training data) and supervised learning (with completely labeled training data).
- Many machine-learning researchers have found that unlabeled data, when used in conjunction with a small amount of labeled data, can produce considerable improvement in learning accuracy over unsupervised learning but without the time and costs needed for supervised learning.
- As you may have guessed, semi-supervised learning algorithms are trained on a combination of labeled and unlabeled data. This is useful for the following  reasons.
	1. the process of labeling massive amounts of data for supervised learning is often prohibitively time-consuming and expensive.
	2. What’s more, too much labeling can impose human biases on the model.
	3. That means including lots of unlabeled data during the training process actually tends to improve the accuracy of the final model while reducing the time and cost spent building it.
- For the above Reasons, semi-supervised learning is a win-win for use cases like webpage classification, speech recognition, or even for genetic sequencing.

#### 4.5 What is required to create a good machine learning systems:
- Data preparation capabilities.
- Algorithms – basic and advanced.
- Automation and iterative processes.
- Scalability.
- Ensemble modeling.
  
#### 4.6 Who's using it ?
- Most industries working with large amounts of data have recognized the value of machine learning technology. Below listed are some of area's Machine Learning models are being used widely.
- **Financial services**:
	- Banks and other businesses in the financial industry use machine learning technology for two key purposes:
	- to identify important insights in data, and prevent fraud.
	- The insights can identify investment opportunities, or help investors know when to trade.
	- Data mining can also identify clients with high-risk profiles, or use Cyber-Surveillance to pinpoint warning signs of fraud.
- **Health care**:
	- Machine learning is a fast-growing trend in the health care industry, thanks to the advent of wearable devices and sensors that can use data to assess a patient's health in real-time. 
	- The technology can also help medical experts analyze data to identify trends or red flags that may lead to improved diagnoses and treatment. 
- **Retail**:
	- Websites recommending items you might like based on previous purchases are using machine learning to analyze your buying history. 
	- Retailers rely on machine learning to capture data, analyze it and use it to personalize a shopping experience, implement a marketing campaign, price optimization, merchandise supply planning, and for customer insights. 
- **Oil and gas**:
	- Finding new energy sources. 
	- Analyzing minerals in the ground. 
	- Predicting refinery sensor failure. 
	- Streamlining oil distribution to make it more efficient and cost-effective. 
	- The number of machine learning use cases for this industry is vast – and still expanding.
    
#### 4.7 Did you know ?
- In machine learning, a target is called a label. where in statistics, a target is called a dependent variable.
- A variable in statistics is called a feature in machine learning.
- A transformation in statistics is called feature creation in machine learning.

# 5.Installing Anaconda and Python in your Machine:
- It is recommended to have at-least machine with 8GB-RAM. i prefer to go with Anaconda since it gives you all the libraries more handy
- Open the following URL in our browser, [Anaconda Installing User Guide](https://docs.anaconda.com/anaconda/install/windows/).
- Find 2 Different types of Installation modes available in the Doc Page as shown below.

<p align="center">
  <img width="756" height="305" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/1-Introduction/References/2TypesOfInstallation.JPG?raw=true">
</p>

- If you are installing Anaconda in your Personal PC/Laptop you can proceed to download Anaconda for Python 3.7 and above, run the .Exe will ask you for Anaconda installation path don't change anything leave things as it and completed the installation.
- Usually installation will take 20-30 min. Please find the below image for your reference.

<p align="center">
  <img width="1043" height="466" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/1-Introduction/References/Anaconda%20Installer.JPG?raw=true">
</p>

- If you want to use anaconda in PC/Laptop which does not have Admin access, recommend to use Minicoda a silent version of Anaconda will install everything by default in the machine. (Note: you are the complete responsibility for this action.)
- please find the below images to Download and install Miniconda in your machine.

<p align="center">
  <img width="1039" height="671" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/1-Introduction/References/Miniconda%20Installer.JPG?raw=true">
</p>


<p align="center">
  <img width="740" height="600" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/1-Introduction/References/Installing%20Miniconda%20-%201.JPG?raw=true">
</p>

- Miniconda Installation command `start /wait "" Miniconda4-latest-Windows-x86_64.exe /InstallationType=JustMe /RegisterPython=0 /S /D=%UserProfile%\Miniconda3`. Here replace the Miniconda version with your version

# 6.How to start with Spyder IDE:
- If you want to get in hand with, Machine Learning and Data Science practices one of the best tool that i can suggest is Spyder IDE, which comes along with Anaconda installation.
- As a pre-requisite before proceeding this topic, i suggest yout to look in to the following link to install anaconda in your machine. [link to install Anaconda](https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/1-Introduction/README.md#5installing-anaconda-and-python-in-your-machine).
- Once you completed installing anaconda in your machine, navigate to start and type Anaconda you will find the following Icon in start menu

<p align="center">
  <img width="211" height="372" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/1-Introduction/References/Windows%20Search.JPG?raw=true">
</p>

- By clicking on above Anaconda Navigator icon will open he following Dashboard screen. 
- please find Spyder IDE and click launch button to launch spyder IDE or simply you can search for sypder in Windows search and launch Spyder IDE.
<p align="center">
  <img width="1363" height="599" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/1-Introduction/References/Anaconda%20Dashboard.JPG?raw=true">
</p>

- Once you open the IDE, it is always recommeded to move to your project directory. to navigate to the project folder use the File Explorer as follows, and create your py file by clicking New file creator icon and set it as your currnet working directory, if you want to shitch Drive use URL navigator in top right corner of the IDE.

<p align="center">
  <img width="1025" height="393" src="https://github.com/ManikandanJeyabal/Machine-Learning-101/blob/master/1-Introduction/References/Spyder%20IDE%20Overview.JPG?raw=true">
</p>

- Image description below:
	1. Open New Py file
	2. Set Current working Directory
	3. File Explorer
	4. URL Navigator
	5. Ipython Console Output
	6. Writing area
	7. Save changes
	
- It is recommended to follow the below steps when you get in handy with Spyder IDE.

	1. Open Spyder IDE
	2. Use file explorer or URL navigator and navigate to your project directory.
	3. open new File
	4. right click and "Set Current working Directory"
	5. type your program in writing area and check your output in IPython console
	6. save your program
