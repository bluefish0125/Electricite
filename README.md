# electricite

### Challenge Goals
The aim is to model the electricity price from weather, energy (commodities) and commercial data for two European countries - France and Germany. The problem here is to explain the electricity price with simultaneous variables and thus this is not a prediction problem. More precisely, the goal of this challenge is to learn a model that outputs from these explanatory variables a good estimation for the daily price variation of electricity futures) contracts, in France and Germany. The metrics of evaluating performance is the spearman correlation coefficient.

### My Approach
I first decided to reduce the skew in the data with transformations, centered & scaled, then I performed PCA on the dataset to capture 95% of variance. Then I used Optuna to perform hyperparameter tuning on my neural network and found parameters that gave me a spearman correlation of 0.317. THe problem that I encountered is that the results of my validation falls significantly short of the result of the hyperparameter tuning. I'm not sure how to proceed!

### Data Description
We provide three csv file data sets: training inputs X_train, training outputs Y_train, and test inputs X_test.

NB: The input data X_train and X_test represent the same explanatory variables but over two different time periods.

The columns ID in X_train et Y_train are identical, and the same holds true for the testing data. 1494 rows are available for the training data sets while 654 observations are used for the test data sets.

Input data sets comprise 35 columns:

ID: Unique row identifier, associated with a day (DAY_ID) and a country (COUNTRY),
DAY_ID: Day identifier - dates have been anonymized, but all data corresponding to a specific day is consistent,
COUNTRY: Country identifier - DE = Germany, FR = France,
and then contains daily commodity price variations,

GAS_RET: European gas,
COAL_RET: European coal,
CARBON_RET: Carbon emissions futures,
weather measures (daily, in the country x),

x_TEMP: Temperature,
x_RAIN: Rainfall,
x_WIND: Wind,
energy production measures (daily, in the country x),

x_GAS: Natural gas,
x_COAL: Hard coal,
x_HYDRO: Hydro reservoir,
x_NUCLEAR: Daily nuclear production,
x_SOLAR: Photovoltaic,
x_WINDPOW: Wind power,
x_LIGNITE: Lignite,
and electricity use metrics (daily, in the country x),

x_CONSUMPTON: Total electricity consumption,
x_RESIDUAL_LOAD: Electricity consumption after using all renewable energies,
x_NET_IMPORT: Imported electricity from Europe,
x_NET_EXPORT: Exported electricity to Europe,
DE_FR_EXCHANGE: Total daily electricity exchange between Germany and France,
FR_DE_EXCHANGE: Total daily electricity exchange between France and Germany.
Output data sets are composed of two columns:

ID: Unique row identifier - corresponding to the input identifiers,
TARGET: Daily price variation for futures of 24H electricity baseload.
The solution files submitted by participants shall follow this output data set format, namely to contain two columns ID and TARGET, where the ID values correspond to those of the ID column of X_test. An example of submission file containing random predictions is provided - see also the notebook in the supplementary material section for the benchmark output.
