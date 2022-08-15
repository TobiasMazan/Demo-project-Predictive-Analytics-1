# Pricing-analysis-demo-project

__1. Project overview__

Public bicycle sharing (PBS) systems are the means of renting bicycles where the process of obtaining membership, rental, and bike return is automated via a network of kiosk locations throughout a city. Using these systems, people are able rent a bicycle from a one location and return it to a different place on an as-needed basis. Maintenance work in continuously functioning system such as PBS would require either shuting down the system for a period of time or performing work interupting the normal bicycle sharing usage- both at risk of customer dissatisfaction. The latter effect can be avoided with better maintenance planning utilizing methods of predictive modelling.

In this demo exercise purpose has been to predict demand for PBS system services in Washington, D.C depending on meteorological data. Of particular interest has been identification of conditions in which traffic would be low enough and weather mild enough to allow for PBS system maintenance.

Solution utilized Jupyter Notebook/Azure Machine Learning; ML algorithms: multiple linear regression, random forest, gradient boosting stack ensemble and data analysis libraries: pandas, matplotlib, numpy, sklearn, seaborn, pickle.

__2. Data collection and preparation__

_2.1. Data collection_

Original data has been taken from web resource: https://thinkingneuron.com/wp-content/uploads/2020/10/CarPricesData.zip

_2.2. Exploratory Data Analysis (EDA)_

Loaded dataset has 8 dimensions and about 2k datapoints. Correlation heatmap revealed several variables likely to have predictive power for 'Price' of used car. It also shows strong multicolinearity in a case of 'Weight' of a car and 'CC' (its engine size):

![image](https://user-images.githubusercontent.com/99291264/164911775-6a991ada-2f39-4593-b99d-7f5b1f66603c.png)

As an example, the scatter for age versus price is relatively low with both correlation coefficient and causal link indicate a negative relationship:

![image](https://user-images.githubusercontent.com/99291264/164911787-6e964a1c-2a5b-4654-9cbf-5f6bf3930fd7.png)

_2.3. Data cleaning_

__3. Predictive Modelling__

_3.1. Baseline models_

![image](https://github.com/TobiasMazan/Pricing-analysis-demo-project/blob/main/Fig%201b.png)

_3.2. Model optimization_

![image](https://github.com/TobiasMazan/Pricing-analysis-demo-project/blob/main/Fig%201.png)

![image](https://github.com/TobiasMazan/Pricing-analysis-demo-project/blob/main/Fig%202.png)

![image](https://github.com/TobiasMazan/Pricing-analysis-demo-project/blob/main/Fig%203.png)

_3.3. Model deployment and utilization_

_3.4. Future work_

__4. Conclusions__


__Resources__










