# Predicting-Google-Trends-Using-Ads-Spending
This project aims to predict Google Trends data for Home Depot to analyze the impact of advertising spending on online search interest. By leveraging time series forecasting models such as SARIMA, SARIMAX, and Prophet, this study provides insights into how marketing investments influence consumer interest over time.


Predicting Google Trends Using Ads Spending
A Comparative Study using SARIMA, SARIMAX, and Prophet Models

Authors
Priyanka Bhosale
Surya Vegesna
Sharmi Pillella
Overview
This project aims to predict Google Trends data for Home Depot to analyze the impact of advertising spending on online search interest. By leveraging time series forecasting models such as SARIMA, SARIMAX, and Prophet, this study provides insights into how marketing investments influence consumer interest over time.

Objective
Predict Google Trends scores for Home Depot.
Assess how ad spending affects online search interest.
Provide marketing insights for better budget allocation and sales forecasting.
Datasets Used
Google Trends Data:

Tracks search interest for Home Depot.
Initial dataset: 1821 rows, key features include date and trend score.
Preprocessing: Removed missing values, renamed columns, and formatted dates.
Home Depot Ad Spending Data:

Captures weekly advertising expenditure across multiple channels.
Original dataset: 756 rows, 13 columns.
Preprocessing: Checked for missing values, standardized column names, and formatted dates.
Data Processing & Preprocessing
Google Trends Data:

Removed missing values.
Converted date format for time series analysis.
Differencing applied to stabilize variance.
ACF and PACF plots used for identifying AR/MA components.
Home Depot Ad Spending Data:

Standardized date formats.
Differencing applied to stabilize the spending trends.
ACF and PACF plots analyzed for stationarity.
Merged Dataset:

Google Trends and Ad Spending data merged on common date column.
Performed correlation analysis between trends and ad spending.
Split dataset into 80% training, 20% testing.
Models Implemented
SARIMA (Seasonal AutoRegressive Integrated Moving Average)

Used ARIMA(2,0,2) model based on ACF/PACF analysis.
Diagnostics: Residual autocorrelation test (Ljung-Box test).
Performance:
RMSE: 2204.43
MAE: 1573.00
MSPE: 7,558,075
SARIMAX (SARIMA with External Regressor - Ad Spending)

Includes TOTAL_DOLLARS (advertising spend) as an external regressor.
Diagnostics: No significant autocorrelation in residuals.
Performance:
MSPE: 7,556,795 (better than SARIMA).
Prophet (Facebook's Time Series Model)

Handles seasonality and changepoints automatically.
Performance:
MSPE: 6,611,852 (best model).
More accurate than SARIMA/SARIMAX due to its flexibility in capturing non-linear trends and seasonal effects.
Model Performance Comparison
Model	External Variables?	Best Fit Order	MSPE (Mean Squared Prediction Error)
SARIMA	No	(2,0,2)	7,558,075
SARIMAX	Yes (Ad Spend)	(1,1,2)	7,556,795
Prophet	Yes (Auto-tuned)	Auto	6,611,852 (Best)
Key Findings
Ad spending impacts online search trends, but models vary in effectiveness.
Prophet performed best in predicting search trends due to its flexibility in handling non-linear trends and seasonality.
SARIMAX performed better than SARIMA by incorporating external regressors (ad spend).
MSPE was lowest for Prophet, making it the most accurate model.
Conclusion & Business Implications
For marketing teams: Optimizing ad spend can significantly improve search interest and increase customer engagement.
For analysts: Time series forecasting with external factors (like ad spend) enhances model accuracy.
For decision-makers: Using Prophet or similar models can improve ROI on advertising budgets.
Technologies Used
Python (pandas, numpy, statsmodels, fbprophet)
Jupyter Notebook
Time Series Analysis (ACF, PACF, Differencing)
How to Run the Project
Clone the repository:
sh
Copy
Edit
git clone https://github.com/your-username/Image-Classification-using-Distributed-Learning.git
cd Image-Classification-using-Distributed-Learning
Install dependencies:
sh
Copy
Edit
pip install pandas numpy statsmodels prophet
Run the Jupyter Notebook:
sh
Copy
Edit
jupyter notebook
Follow the notebook instructions to execute data preprocessing, modeling, and evaluation.
Future Enhancements
Integrate deep learning models (LSTMs, Transformer-based models).
Experiment with feature engineering on ad spend categories.
Use more granular ad spend data (e.g., daily spend per platform).
Acknowledgments
Special thanks to the authors and contributors for their research and development efforts.

