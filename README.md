# Used-Cars-Predictions

## Goal
Goal: predict the price of used cars based on various attributes. The project scores were calculated with the RMSE (Root Mean Squared Error) metric 

## Dataset
Car Price Prediction Dataset is a comprehensive collection of automotive information extracted from The following [website](https://www.cars.com.) This dataset comprises 4,009 data points, each representing a unique vehicle listing, and includes nine distinct features providing insights into the world of automobiles.

## EDA
The most glaring problem in the data is the outliers. It can be seen by visualizing the target column.
![image](https://github.com/user-attachments/assets/5942de6e-8744-432f-98c8-f96b68f213ee)
There are a few outliers that skew some of the metrics and might lead to suboptimal results.
Therefore there are two possible directions, either cap the target column and lose valuable information, or focus the entire project on finding the features that define those outliers the best.  

## Feature Engineering 
The dataset contained a couple of dirty features. In addition, there was a need to define the outliers (the expensive cars) and find out what made them stand out.
Therefore during the project, I created two main groups of new features. The first group consists of features that comprise the dirty column. For example, this raw "engine" data was turned into this "355.0HP 5.3L 8 Cylinder Engine Gasoline Fue" --> horsepower:355, engine_size:5.3, cylinders: 8. The second group is the luxury features. These groups of features try to capture the outliers as it is shown that they might have distinct characteristics.
![image](https://github.com/user-attachments/assets/34c41ed8-730f-4825-bdc6-e09ff0e214c8)

## Modeling 
The final solution was an ensemble of the following regression models XGBoost, LightGBM, CatBoost, RandomForest, GradientBoosting, and Linear regression. This solution provided the most robust solution as it combines models that are capable of capturing different 
 
## Tuning
The tuning process first involved using the optuna package to tune the hyperparameters of each model individually. The next step is to tune the ensemble weights, to find the best combination that will lead to the optimal result. I experimented with genetic algorithm weight but ultimately chose to use optuna for the weight tuning as it brought me the best result.
