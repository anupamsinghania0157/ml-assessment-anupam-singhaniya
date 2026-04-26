# B1. Problem Formulation

## (a)
The target variable is items_sold. The input features include promotion type, store size, location type, competition density, and time-based features like month and day of week. This is a regression problem because we are predicting a continuous numerical value (items sold).

## (b)
Revenue depends on price and discounts, which may vary across promotions. Items sold is a better target because it directly measures customer demand. This highlights the principle that the target variable should closely align with the business objective.

## (c)
Instead of using a single global model, we can use store-level segmentation or include location-based features. Another approach is to build separate models for different store clusters to capture varying customer behavior.

# B2. Data and EDA Strategy

## (a)
The tables can be joined using store_id and transaction_date as common keys. The final dataset will have one row per store per day. Aggregations such as total items sold per day, average basket size, and promotion indicators can be created before modeling.

## (b)
EDA would include:
- Sales distribution by promotion type  
- Sales trends over time  
- Comparison of sales across store locations  
- Correlation analysis  

These insights help in feature engineering and model selection.

## (c)
The imbalance where most transactions have no promotion may bias the model. To address this, we can use resampling techniques, apply weights, or analyze promotion effectiveness separately.

# B3. Model Evaluation and Deployment

## (a)
A time-based split should be used, where earlier data is used for training and recent data for testing. Random split is inappropriate because it can lead to data leakage. Evaluation metrics include RMSE and MAE.

## (b)
Feature importance helps explain why different promotions are recommended. Seasonal factors like December holidays may influence results differently compared to other months.

## (c)
The model can be saved using joblib. New monthly data is processed using the same pipeline and fed into the model. Monitoring includes tracking errors and detecting performance drops for retraining.
