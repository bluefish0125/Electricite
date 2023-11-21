# electricite

### Challenge Goals
The aim is to model the electricity price from weather, energy (commodities) and commercial data for two European countries - France and Germany. The problem here is to explain the electricity price with simultaneous variables and thus this is not a prediction problem. More precisely, the goal of this challenge is to learn a model that outputs from these explanatory variables a good estimation for the daily price variation of electricity futures) contracts, in France and Germany. The metrics of evaluating performance is the spearman correlation coefficient.

### My Approach
In the initial preprocessing phase, I prepared the dataset for Principal Component Analysis (PCA) by employing skewness-reducing transformations and ensuring uniformity through centering and scaling procedures. Subsequently, I conducted a series of experiments utilizing Lasso regression for effective feature selection and further employed PCA for dimensionality reduction. These steps aimed to distill the most relevant information from the dataset. In pursuit of optimizing model performance, I leveraged Optuna for hyperparameter tuning on neural networks and random forest algoritms.

### My Result
After an exhaustive search in the hyperparameter space and different preprocessing subsets of data, the resulting configuration yielded a Spearman correlation coefficient of 0.35, indicating a moderate positive monotonic relationship between the predicted and actual values. In the specific context of daily volaility of european electricity futures, a spearman correlation of 0.35 is significant. 
