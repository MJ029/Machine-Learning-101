# Data Imputation

### What is Imputation ?
- In statistics, imputation is the process of replacing missing data with substituted values. 
- Substituting for a data point, it is known as "unit imputation".
- Substituting for a component of a data point, it is known as "item imputation"
- Main Problems:
	- missing data can introduce a substantial amount of bias.
	- make the handling and analysis of the data more arduous.
	- create reductions in efficiency.
- Imputation preserves all cases by replacing missing data with an estimated value based on other available information.
- Once all missing values have been imputed, the data set can then be analyzed using standard techniques for complete data.
- There have been many theories embraced by scientists to account for missing data but the majority of them introduce bias. A few of the well known attempts to deal with missing data include:
	- hot deck and cold deck imputation
	- list-wise and pair-wise deletion
	- mean imputation
	- non-negative matrix factorization
	- regression imputation
	- last observation carried forward
	- stochastic imputation
	- multiple imputation
- Other Imputation techniques such as MICE, KNN, missforest, Fuzzy K-Means Clustering also can be used for imputation

### 1. Single Imputation:
#### 1.1 Mean Imputation:
- Mean Imputation technique involves replacing any missing value with the mean of that variable for all other cases.
- This has the benefit of not changing the sample mean for that variable.
- But the variability in the data is reduced, so the standard deviations and the variance estimates tend to be underestimated.
- The magnitude of the co-variances and correlation also decreases by restricting the variability and this method often causes biased estimates.

#### 1.2 Hot-Deck Imputation:
- Hot-Deck Imputation is one of the simplest single-imputation methods.
- Here each missing value is replaced with an observed response from a "similar" unit.
- The term "hot deck" dates back to the storage of data on punched cards, and indicates that the information donors come from the same data-set as the recipients
- Hot deck imputation involves replacing missing values of one or more variables for a non-respondent (called the recipient) with observed values from a respondent (the donor) that is similar to the non-respondent with respect to characteristics observed by both cases.
- In some versions, the donor is selected randomly from a set of potential donors, which we call the donor pool; we call these methods random hot deck methods.
- In other versions a single donor is identified and values are imputed from that case, usually the "nearest neighbor" based on some metric; we call these methods deterministic hot deck methods.
- One form of hot-deck imputation is called "last observation carried forward" (or LOCF for short), which involves sorting a data-set according to any of a number of variables, thus creating an ordered data-set. The technique then finds the first missing value and uses the cell value immediately prior to the data that are missing to impute the missing value. The process is repeated for the next cell with a missing value until all missing values have been imputed.
- This method is known to increase risk of increasing bias and potentially false conclusions. For this reason LOCF is not recommended for use.

#### 1.3 Cold-Deck Imputation:
- A systematically chosen value from an individual who has similar values on other variables. Basically it selects donors from another dataset. 
- This is similar to Hot Deck in most ways, but removes the random variation.

#### 1.4 Non-negative matrix factorization:
- Non-negative matrix factorization (NMF or NNMF), also non-negative matrix approximation,  is a group of algorithms in multivariate analysis and linear algebra where a matrix V is factorized into (usually) two matrices W and H, with the property that all three matrices have no negative elements.
- This non-negativity makes the resulting matrices easier to inspect.
- Also, in applications such as processing of audio spectrograms or muscular activity, non-negativity is inherent to the data being considered
- NMF finds applications in such fields as astronomy, computer vision, document clustering, missing data imputation, chemometrics, audio signal processing, recommender systems, and bioinformatics.

#### 1.5 Regression:
- Regression imputation has the opposite problem of mean imputation.
- A regression model is estimated to predict observed values of a variable based on other variables, and that model is then used to impute values in cases where the value of that variable is missing.
- In other words, available information for complete and incomplete cases is used to predict the value of a specific variable. 
- Fitted values from the regression model are then used to impute the missing values.
- The problem is that the imputed data do not have an error term included in their estimation, thus the estimates fit perfectly along the regression line without any residual variance.
- This causes relationships to be over identified and suggest greater precision in the imputed values than is warranted. 
- The regression model predicts the most likely value of missing data but does not supply uncertainty about that value.
- Stochastic regression was a fairly successful attempt to correct the lack of an error term in regression imputation by adding the average regression variance to the regression imputations to introduce error. 
-  Stochastic regression shows much less bias than the above-mentioned techniques, but it still missed one thing – if data are imputed then intuitively one would think that more noise should be introduced to the problem than simple residual variance.

### 2. Multiple Imputation:
