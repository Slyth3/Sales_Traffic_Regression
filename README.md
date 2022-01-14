Predicting Sales and Foot Traffic of an Anonymous US Based Company Using LightGBM and Ridge Models

Andrew Schleiss

1.
# ![Shape1](RackMultipart20220114-4-1ryo50e_html_c186f39763cdc4c6.gif)
ProblemIntroduction

The problem is split into two parts, the prediction of both Sales as well as foot Traffic\* for the company at 1-hour intervals for the following month.

An initial exploration of the data was completed to understand seasonality, trends and correlations as well conceptualize the methods for data engineering/extracting and modelling techniques.

Date engineering techniques used can be surmised under two formats: temporal feature extraction (day, month, year, etc.) and Fourier decomposition extraction (sine and cosine expressions).

The two models selected include a linear regularised model (Ridge) and a tree based gradient boosting model (LightGBM). The Traffic data was initially modelled and predicted to be used in the prediction of the Sales data which ultimately improved the accuracy of the prediction.

LightGBM outperformed Ridge with highest R-squared scores for both Sales and Traffic data, with a value of 0.96 and 0.86 respectively for one month validation.

\*All data and requirements were provided by REPL

1.
# ![Shape2](RackMultipart20220114-4-1ryo50e_html_6a1a59b4a5a212bf.gif)
Datasets

Training Data

TrainingdatafromREPL was received, which included two training files in csv format for Sales and Traffic values against their captured dates. A sample of the Sales data can be seen below:

![](RackMultipart20220114-4-1ryo50e_html_2518061a6638f690.png)

Sample of the Sales data at 15min intervals

The values were captured at 15-minute intervals during business hours (assumption). There were multiple timeframes missing or not captured for specific periods as well as 0\* values captured for Traffic data.

Test Data

1-month prediction timeframes were extrapolated using the Sales and Traffic data respectively for each prediction. As such, the Test data contains the same hourly intervals as that of the previous month.

![](RackMultipart20220114-4-1ryo50e_html_578017af16a3e037.png)

Code for the creation of Sales Test data at 15min intervals

\*Assumed to be the missing values as outlined in the exercise document

Additional Data

Yearly Gross Domestic Product ( **GDP** ) values were obtained as these values were expected to relate to spending power, and as a result, Sales; however the feature importance of the models show this is not the case, albeit with additional location information about the company we could improve this dataset at a state/city level.

US federal **holidays** were merged to training data as they should indicate days where customers would be more likely to make purchases.

1.
# ![Shape3](RackMultipart20220114-4-1ryo50e_html_c186f39763cdc4c6.gif)
Features andProcessing

Missing Values

The initial assumption was that the missing values were those values identified as 0 (zero)

Upon further investigation the missing values are those with missing 15-minute time intervals. These intervals are assumed missing because there were no sales or traffic during these time (i.e., after business hours)

These missing values were set to 0 through the 1-hour **resampling** method, as such, these values do not need to be interpolated. The previous method for interpolation still holds true for time series and I will keep the section below for reference:

_ **Prior** _ _to resampling, the missing values were imputed using interpolation, either with_ _ **linear** _ _or the_ _ **cubic spline** _ _methodologies. Linear interpolation, as it suggests, creates a linear polynomial line between the points before and after the missing value, with a value identified between the two. Cubic spline uses all the features in its prediction and creates_ _ **n** _ _polynomial lines (spline) through data of polynomial degree 3 (cubic). Although there were several other methods for interpolation these two methods should give sufficient varied results._

_One downside to interpolation relates to missing values present in the initial or first points in the dataset, as seen in the supplied data. This is because there are no prior values to use in the calculation._

_As a result, backfill_ _ **interpolation** _ _can be used to set these values._

Resampling

Predictions were required at hour intervals however the training data was at 15-minute intervals; the data was therefore resampled with summation at 1-hour intervals. The resampling process causes several 0 values as it created intervals even where there was nothing captured in that hour.

These 0 values must not be confused with the missing values present in the data.

Date Decomposition

**Temporal features** were extracted and extrapolated into fields:

_hour, day, month, year month start indicator, month end indicator, day of the week, week in year, day of year, days in month_ and _inverse day of year_

Additional temporal features were created to indicate specific months at the end of the year, as high variances in the data were identified during these periods (_October, November, December, and January_) as they hold the most holidays dates, New Years and Christmas.

Days falling on _Friday, Saturday_ and _Sunday_ were also extracted as well as each _quarter_ of the year.

**Fourier decomposition (linear features)** was applied using Sine and Cosine functions on the minute, hour, day and month values to extract seasonality.

Next Holiday

Using the holiday values (obtained from the federal holiday data) the number of days until the _next holiday_ was calculated; this was calculated as a ramp up of sales/traffic leading up to important holidays would be expected.

1.
# ![Shape4](RackMultipart20220114-4-1ryo50e_html_6a1a59b4a5a212bf.gif)
Metrics

The metrics used in this exercise included two metrics used for training and analysis:

- Root Mean Square Error (RMSE) – needed to minimize
- R-squared (R2) – needed to maximize

RMSE was used as the intrinsic model evaluation metric (if required) and for performance analysis with R2. These two metrics were selected together as they give an overall indication of the trend and error rate of the resulting predictions.

R-squared measures the predictions against a horizontal null hypothesis. This reveals whether the predictions are &#39;trending&#39; away from a general horizontal line and towards the overall direction of the true values.

RMSE indicates the error rate or difference between the actual and predicted values.

In isolation, RMSE is a good indicator for model performance, however, where there are very large or very small outliers in the training data this value could be exacerbated and may give a bad indication of the model&#39;s performance, therefore R2 was used to counter this as it will follow the over &#39;trend&#39; of the predictions to the actual values.

1.
# ![Shape5](RackMultipart20220114-4-1ryo50e_html_6a1a59b4a5a212bf.gif)
Modelling Techniques

Initial Model Selection

During the initial EDA process an auto-ml package called Pycaret was used to run multiple machine learning models on the Sales data. This provided an indication of the types of models to be used. The results are below:

![](RackMultipart20220114-4-1ryo50e_html_c23180e065a52b37.png)

Pycaret run on raw Sales data

The above shows that gradient boosting trees could be potential models for this problem, however, this baseline doesn&#39;t include several additional features and processing which is required in the final models. It also wasn&#39;t run for Traffic; therefore a Linear model will be selected as well.

**LightGBM** - was used for predicting Traffic and Sales, as this model has done well in several recent competitions [1] due to its fast processing and highly accurate results.

**Ridge**** Regression** – multiple linear models were tested (Huber, Tweedie) with the best being Ridge Regression. It was hypothesised that this was a result of the model&#39;s ability to apply _regularization_. Regularization was beneficial as there were multiple extracted additional features; this may result in a noisy dataset if not weighted correctly.

Merge of Traffic and Sales

It was assumed that Sales is the primary prediction required as Sales has a direct impact on company revenue, as such and from the feature importance from the pycaret baseline, Traffic data was added to the Sales data.

![](RackMultipart20220114-4-1ryo50e_html_44ec309bfe9dee6b.png)

Pycaret baseline feature importance

Hyperparameter Tuning

The process for hyperparameter tuning was either done by **Optuna** for LightGBM or via an **iterative** process of trial-and-error for Ridge.

Optuna a hyperparameter optimization framework was setup with a range of influential LightGBM parameters [2] and run for 300 trials with a pruning callback stop poor trials. The output of Optuna provided optimal parameters to minimize RMSE.

Validation Hold-Out

Hold-out validation method was used, with 1 month of training data being held for validation purposes as this is the same timeframe required for prediction.

**Note** : Poor performance has been experienced with timeseries cross validation testing as initial folds with poor performance dilute the additional folds (with better performance).

![](RackMultipart20220114-4-1ryo50e_html_557c9e074a6e3452.png)

Traffic training and validation hold-out

Experimental Runs

A number of &#39;experiments&#39; were run, and their resulting RMSE and R2 score recorded. A full list of these runs can be provided on request with a number of important runs stated in their relative notebooks.

A set of experiments were to test:

- Temporal and Linear Features
- Adding public holidays
- Adding GDP
- Adding Traffic data (Sales prediction only)
- Split of train, validation data at different time intervals
- Interpolation methods – linear, cubic spline, backfill
- Scaling methods – Standard, MinMax or Robust Scaling

Traffic Modelling Process

The modelling technique involved training and predicting Traffic data. This data would then be used in the prediction of Sales with the assumption that a higher number of customers in store will equate to higher sales.

![](RackMultipart20220114-4-1ryo50e_html_e87f3a33a67fd79c.png)

Traffic model process

**LightGBM** had better performance in predicting the **future** Traffic values and **Ridge** predicted better on **historical values** ,as such Traffic data was split into three:

- Historical data – predicted by Ridge
- Actual data – provided by REPL
- Future prediction – predicted by LightGBM and used as submission

See results section for details.

![](RackMultipart20220114-4-1ryo50e_html_7941d718b4561963.png)

Traffic and Sales data overlap and prediction indicator(green)

Due to the mismatch in timeseries of Traffic and Sales data, historical and future predictions for Traffic values were predicted and added to the Sales data (for prediction of Sales).

Sales modelling process

Sales were predicted using the same features extracted for Traffic as well as comparing the two models.

![](RackMultipart20220114-4-1ryo50e_html_140c9ee06f64ef46.png)

Sales model process

LightGBM performed better than Ridge, with the assumption that LightGBM performs better in short term predictions and future values whereas Ridge preforms better in longer prediction horizons and historical predictions.

Ensembling

Two ensembling techniques were used for predicting Sales data\*

- Arithmetic mean
- Geometric mean

Arithmetic mean sums the prediction values from each model&#39;s submission and divides this by the number of submissions.

![](RackMultipart20220114-4-1ryo50e_html_65777a90d305003d.png)

Geometric mean takes the nth root of the multiplicative of the predictions where n is the number of submissions.

![](RackMultipart20220114-4-1ryo50e_html_d4548622c441aea8.png)

Geometric mean is preferred when the values are exponential and have constant growth, otherwise arithmetic mean is preferred.

\*Only LightGBM was used to predict Sales data as Ridge did not perform well on future values

1.
# ![Shape6](RackMultipart20220114-4-1ryo50e_html_c186f39763cdc4c6.gif)
Results andDiscussion

The best performing experiments are below for each model and dataset.

Best Validation Testing Results

| **Data** | **Model** | **RMSE** | **R-Squared** |
| --- | --- | --- | --- |
| Traffic | LightGBM | 3.56 | **0.87** |
| Traffic | Ridge | 5.95 | 0.65 |
| Sales | LightGBM | 275.92 | **0.97** |
| Sales | Ridge | 608.20 | 0.84 |

Traffic Predictions

Traffic predictions were split into two parts for the future (submission) predictions and the historical predictions.

![](RackMultipart20220114-4-1ryo50e_html_1ccc7c416ba24c0f.png)

**Ridge** predictions for Traffic data

![](RackMultipart20220114-4-1ryo50e_html_a49a6f1df0f201f1.png)

**LightGBM** predictions for Traffic data

For the 1-month validation test, Ridge performed worse than LightGBM on **future** predictions, however when visualizing the historical predictions, Ridge was able to interpret the data better for longer periods.

![](RackMultipart20220114-4-1ryo50e_html_7cc1f711769bb122.png)

**Ridge** and **LightGBM** predictions for Traffic data

Therefore, Ridge was used to predict the historical values and LightGBM to predict the future (submission) values.

Sales Predictions

LightGBM bested Ridge with a higher R-Squared and lower RMSE. The main differing influences being LightGBM preferred temporal features (linear features removed), whereas Ridge preferred the Fourier features (temporal features removed).

![](RackMultipart20220114-4-1ryo50e_html_ad01e9b2bcba9ee4.png)

**LightGBM** predictions for Sales data

![](RackMultipart20220114-4-1ryo50e_html_42b3f770db818c3a.png)

**Ridge** predictions for Sales data

Ensembling Results

Sales final predictions were ensembled using the submissions of the Ridge model and LightGBM model.

**Arithmetic mean** ensembling was used as the final submission as it predicted higher than geometric mean ensembling, due to the assumption that all models are underpredicting.

![](RackMultipart20220114-4-1ryo50e_html_bbf865420a538af8.png)

**Arithmetic** Ensemble with LightGBM reference

**Note** this was not an optimal ensembling technique and was used for demonstration purposes only.

To improve on this technique, multiple submissions should be saved and used for **each model** and then ensembled.

1.
# ![Shape7](RackMultipart20220114-4-1ryo50e_html_c186f39763cdc4c6.gif)
Reflection

This was an interesting and challenging exercise which I enjoyed tremendously; the biggest hurdles were getting the Traffic data into a format for Sales to use as well as resampling the data into hour intervals.

If time allowed, I would have also attempted the below to improve performance:

- Multi-step recursive prediction on a 7-day horizon
- 7-day value lags (shift Sales and Traffic values)
- Further ensembling with additional models and submissions

#

1.
# ![Shape8](RackMultipart20220114-4-1ryo50e_html_c186f39763cdc4c6.gif)
Assumptions

There were some questions related to the exercise requirements. The below assumptions were requested for clarification however clarity wasn&#39;t provided as of writing this document.

- Data was presented at 15-minute intervals, the exercise asked for 1-hour intervals. As such the data was resampled to 1-hour intervals.
- 1 month prediction was required however the training data did not end at 1 month, therefore the prediction timeframe was created and projected 1-month from the last day of the training.
- Missing values were said to be present in the datasets and were assumed to be all intervals not present in the 15-minute timeframe

1.
# ![Shape9](RackMultipart20220114-4-1ryo50e_html_c186f39763cdc4c6.gif)
References

1. LightGBM in 2nd place in M5 competition [https://www.kaggle.com/c/m5-forecasting-accuracy/discussion/164599](https://www.kaggle.com/c/m5-forecasting-accuracy/discussion/164599)
2. LightGBM parameter tuning [https://lightgbm.readthedocs.io/en/latest/Parameters-Tuning.html](https://lightgbm.readthedocs.io/en/latest/Parameters-Tuning.html)
3. GDP Data [https://data.worldbank.org/indicator/NY.GDP.MKTP.CD](https://data.worldbank.org/indicator/NY.GDP.MKTP.CD)
4. US federal Holidays [https://data.world/sudipta/us-federal-holidays-2011-2020](https://data.world/sudipta/us-federal-holidays-2011-2020)
