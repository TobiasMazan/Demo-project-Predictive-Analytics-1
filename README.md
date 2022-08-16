# Pricing-analysis-demo-project

__1. Project overview__

Users of the used automobiles marketplace are unsure about how attractive a given car for sale entry is as compared to other offers. As a result engagement and retention metrics of the portal are falling.

In this demo exercise purpose has been to predict price for secondary market automobile depending on its key characteristics and assess attractiveness of the offer to guide portal users. 

Solution utilized Jupyter Notebook; ML algorithms: multiple linear regression, deep neural network and data analysis libraries: pandas, matplotlib, numpy, sklearn, tensorflow, keras, seaborn, pickle.

__2. Data collection and preparation__

_2.1. Data collection_

Original data has been taken from web resource: https://thinkingneuron.com/wp-content/uploads/2020/10/CarPricesData.zip

_2.2. Exploratory Data Analysis (EDA)_

Loaded dataset has 8 dimensions and about 2k datapoints. Correlation heatmap revealed several variables likely to have predictive power for 'Price' of used car. It also shows strong multicolinearity in a case of 'Weight' of a car and 'CC' (its engine size):

![image](https://user-images.githubusercontent.com/99291264/164911775-6a991ada-2f39-4593-b99d-7f5b1f66603c.png)

As an example, the scatter for age versus price is relatively low with both correlation coefficient and causal link indicating a negative relationship:

![image](https://user-images.githubusercontent.com/99291264/164911787-6e964a1c-2a5b-4654-9cbf-5f6bf3930fd7.png)

_2.3. Data cleaning_

In order to prepare data for further analysis following actions have been performed:
  * Elimination of data points with missing values for 'Price' variable,
  * Replacing incorrect values (price of the car < 0) with mean value in a dataset, 
  * Removing duplicates based on 'KM' variable,
  * Removing redundant variables: those that show strong dependency on another variable in a dataset removed from linear regression baseline model ('Weight' showed stronger relation with target variable than 'CC'- engine size)      

__3. Predictive Modelling__

_3.1. Baseline models_

Model response (target) variable ('Price') as well as predictor variables ('Age', 'KM', 'Weight', 'HP', 'MetColor', 'Doors') have been defined. Train-test split and then basic linear regression model has been initiated and trained. As a null model prediction of mean 'Price' for each data point has been taken. Root mean squared error (RMSE) has been used as model error metric. 

In an example run linear regression beats null model nearly 3 times. Prediction visualizations between response and predictor variables question however validity of the selected linear regression baseline model. While predictive power of each individual predictor variable is limited by multivariable nature of the analyzed problem, for the main predictor ('Age') only the predicted magnitude is close to observation, but not the relationship shape: 

![image](https://github.com/TobiasMazan/Pricing-analysis-demo-project/blob/main/Fig%201.png)

_3.2. Model optimization_

In order to improve quality of the baseline model _Deep Neural Network (DNN)_ model have been employed together with _feature selection_ and _hyperparameter tuning_ methods.

Performing feature selection _for_ loop invoking _SelectKBest_ filtering method has been initiated. It revealed that no particular number of predictor variables (features) consistently shows to minimize root mean squared error (RMSE). Therefore no modification to original dataset has been required.  

The hyperparameter tuning has been performed in cloud using cross validation grid search (_GridSearchCV_) and _neg mean absolute percentage error_ scoring function. Finally, best model has been found for hyperparameters- {'batch_size': 10, 'epochs': 20, 'optimizer': 'RMSprop'} beating the linear regression model by 8%. This advantage was exhibited in fidelity of DNN predicted relationship shape to the observed one:

![image](https://github.com/TobiasMazan/Pricing-analysis-demo-project/blob/main/Fig%202.png)

![image](https://github.com/TobiasMazan/Pricing-analysis-demo-project/blob/main/Fig%203.png)

![image](https://github.com/TobiasMazan/Pricing-analysis-demo-project/blob/main/Fig%204.png)

_3.3. Model deployment and utilization_

The best performing model has been deployed as offline application using _pickle.dump_ method. Then it has been loaded back in order to make predictions. 

__4. Conclusions__

Approach taken here achieved nearly 300% improvement of null model, further 8% improvement compared to linear regression baseline model and good prediction curve shape fidelity. This suggests that ML model deployed as an independent application can reasonably output market value of secondary market car if trained on dataset of similar class vehicles. Therefore it can be successfully used to assign "market price", "above market" and "below market" designations to each car for sale entry in the web portal.

__Resources__










