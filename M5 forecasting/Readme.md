The M5 forecasting comeptition held on kaggle
Point forecasts - https://www.kaggle.com/c/m5-forecasting-accuracy
https://mofc.unic.ac.cy/m5-competition/

Problem: Time Series Forecasting

Data files are too big to be added here, please downlaod from kaggle link if needed

EDA.ipynb - plot ith series (by item and store) 

Created validation_values.csv to compare predictions for validation data
Evaluate.ipynb - copied code for calculating public leaderboard score WRRMSSE

###### Aggregated the series at store and department level and after prediction used 28 day historical proportions to forecast individual series

Implemented prophet model 
    prophet.ipynb - exploring different time series with plots 
    prophet_full.ipynb - full model for submission, WRRMSSE (validation) - 0.79607

Implemented gradient boosted regressor model 
    gbt.ipynb - exploring different time series with plots
    gbt_full - full model for submission, WRRMSSE (validation) - 0.70735
    

###### Predicting all series individually

m5-lightgbm_eval.ipynb - Microsoft's LightGBM model to predict all (30490) series individually
This is for final prediction for submission(evaluation set)
This achived a private LB score of 0.63130 [**214th out of 5558, Silver medal - Top 4%**]
WRRMSSE in validation phase was 0.54941
