# titanicForest
multi-label binary classification problem, dataset from kaggle, random forest implementation

Problem:
to complete the analysis of what sorts of people were likely to survive in the sinking of the Titanic by applying the tools of machine learning to predict which passengers survived the tragedy.

Implementation:
Using Random Forest Classification algorithm,
Using pandaa as data structure

Reason for choice of algorithm:
Random Forest Classification gives more accurate and stable prediction

Source of data: https://www.kaggle.com/c/titanic/data

Method:
1 Import the data
2 Separating the numerical variable data, we only analyse this part first
    2.1 Data Cleaning: Filling missing values with the mean of the available data for that variable
    2.2 Data Reduction: Examining the data for irrelevant information we find that there is none
    2.3 Create the model based on this data (training)   
    2.4 Computing and noting the C-stat value (testing)
3 Now considering the categorical variable data
    3.1 Data Cleaning: Filling missing values with "missing" string
    3.2 Data Reduction: Irrelevant variables like "name", "passengerId" are dropped
    3.3 Data manipulation: Creating dummy variables and then dropping original variables so that data has only integer values
    3.4 Creating a model based on the categorical as well as numerical data (training)
    3.5 Computing and noting the C-stat value (testing)
4 Exploratory analysis:
    4.1 Calculating feature importances and plotting a horizontal bar graph
    4.2 Parameter tuning:
        4.2.1 n_jobs: using timeit we compute c_stat for n_job=1 and -1, compare , select
        4.2.2 n_estimators: computing c_stat values for different number of trees(n_estimators), plot graph on c-stat values, select
        4.2.3 max_features: computing c_stat values for different number of features(max_features), plot graph on c-stat values, select
        4.2.4 min_samples_leaf: computing c_stat values for different number of nodes, plot graph on c-stat values, select
5 Final Model: 
    5.1: Creating a model based on the selected values for respective parameters (training)
    5.2: Computing the C-stat value for the final model
    

Observation (c-stat values) :
1 for model using numerical variables data: 0.7399551550399983
2 for model using numerical as well as categorical variables data: 0.8635211282608464
3 for final model:  0.8742690058479532

Conclusion:
1 when we have more relevant information, the accuracy increases (comparing observations 1 & 2)
2 maximum c_stat value that can be achieved using Random Forest Classification is 0.8742690058479532

By:
1 Bhavana Mache
2 Kinjal Parikh
