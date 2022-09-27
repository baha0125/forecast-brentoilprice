# forecast-brentoilprice
**1. The dataset and main objective**

The dataset was retrieved from US Energy Information Administration, but it was downloaded from kaggle (https://www.kaggle.com/datasets/mabusalah/brent-oil-prices) and containt price of oil from 1987 to 2021. The main goal of this project is to predict the oil price from this dataset.

**2. Test Harness**

Test harness must be developed for investigate data and evaluate model. This involves two steps:
- Defining a validation test
After resampling dataset, we could get monthly price of oil, we obtain total number of dataset is 405 and then we split the dataset into validation and evaluation dataset with ratio 5:95.
- Developing a method for model evaluation
Evaluation dataset will be used for model evaluation. The strategy of model evaluation can be seen in flowchart below.

**3. Exploratory Data Analysis**

Exploratory data analysis is used to analyze and investigate data sets and summarize their main characteristics. The results of visualization of time series give some points:
- There is an increasing trend of oil price
- There do not appear to be any obvious outliers
- The distribution of time series does not follow gaussian distribution, but exponential distribution.
- The adfuller test shows that the time series is not stationary

**Line plot and adfuller test time series:**
<img src="https://raw.githubusercontent.com/bahategar/forecast-brentoilprice/main/image/Screenshot%202022-09-27%20130620.png">

**Distribution of time series:**

<img src="https://raw.githubusercontent.com/bahategar/forecast-brentoilprice/main/image/Screenshot%202022-09-27%20130525.png">

**4. Model Evaluation**

The steps of model evaluation are below:

i. The evaluation dataset will be splitted into train dataset and test dataset with ratio 80:20

ii. The train dataset will be used to train the model after transformed it

iii. The test dataset will be iterated (The walk-forward validation) and test the model after training the model finish

iv. The predictions made during the iteration of the test dataset will be evaluated using RMSE measurement.


**The result of ARIMA model:**

<img src="https://raw.githubusercontent.com/bahategar/forecast-brentoilprice/main/image/Screenshot%202022-09-27%20130903.png">


**The result of residual analysis:**

<img src="https://raw.githubusercontent.com/bahategar/forecast-brentoilprice/main/image/Screenshot%202022-09-27%20130919.png">

The model result and residual analysis show that the model that proposed give a good result. In addition, the baseline model (persistence model) give RMSE results 5.3, a little higher than ARIMA model.

**5. Model Validation**

The model validation includes the following steps:

i. Finalize model: Train and save the final model

ii. Make prediction: Load the finalize model and make a prediction

iii. Validate model: Load and validate the final model

The result of validation model gives positive result as visualized below:

<img src="https://raw.githubusercontent.com/bahategar/forecast-brentoilprice/main/image/Screenshot%202022-09-27%20130939.png">
