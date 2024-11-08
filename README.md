# Taxi Order Forecasting

**Project Overview:**

The "Sharp Taxi" company has gathered historical data on taxi orders at airports. To attract more drivers during peak times, it's essential to predict the number of taxi orders for the upcoming hour. The task is to build a model that forecasts the number of orders based on past data.

The performance metric for this project is the RMSE (Root Mean Squared Error), and the target is to achieve an RMSE of no more than 48 on the test dataset.

**Research Steps:**

1. Load the data and resample it to an hourly frequency.
2. Perform exploratory data analysis (EDA) and data preprocessing.
3. Train different machine learning models with various hyperparameters. The dataset will be split into a training set (90%) and a test set (10%).
4. Evaluate the models on the test set and analyze the results.

**Data Description:**

The dataset is provided in a file called `taxi.csv`. The number of taxi orders is located in the `num_orders` column. The data spans from March 1, 2018, to August 31, 2018.
The dataset used for this project is part of a course and cannot be shared publicly.

**Conclusion:**

1. The data has been successfully loaded, dates set as indices, and the period ranges from 2018-03-01 00:00:00 to 2018-08-31 23:50:00. Resampling was performed with a one-hour frequency (the number of orders was summed).
2. Data analysis revealed the following:
   - From March to August, the number of taxi orders increased.
   - A cyclic pattern was observed in the number of orders each day: more orders during the evening and a drop at night.
3. Features were created for the model: hour, day, month, weekday, 24 lag features, and a 12-day moving average.
4. Three models were trained:
   - **Model 0**: Linear Regression (Ridge) – Best RMSE on cross-validation: 27.11
   - **Model 1**: Gradient Boosting with CatBoost (tuning iterations) – Best RMSE on cross-validation: 26.29
   - **Model 2**: Decision Tree – Best RMSE on cross-validation: 30.21
   The gradient boosting model with CatBoost showed the lowest RMSE and was selected as the best model.
5. Predictions were made on the test set, with the RMSE on the test data being 44.86, which is within the target threshold of 48.

**Model Performance:**

- **RMSE on the test dataset**: 44.86
- The best model was achieved using CatBoost Gradient Boosting, with the lowest RMSE across all tested models.

**Future Work:**
- Explore more advanced models (e.g., XGBoost, LSTM) to improve performance.
- Analyze the impact of weather or holiday events on the number of taxi orders.
