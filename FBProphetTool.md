# 'Prophet' -- its free forecasting tools -- for Python

Producing high quality forecasts is not an easy task  for most analysts. To achieve high quality forecast is difficult due to the following:

      1.Difficulty in incorporating useful assumptions or heuristics to an automated forecast.

      2.Hihly spaecialized skill requirement,which many analysts do not have and are very difficult to find.

Due to the above challenges the demand for high quality forecast outstrips the pace or the skills available to produce them hence prophet was created.

## Prophet

Prophet is a forecast procedure implemented in python and R. It was created by facebook for the purposes of forcast and decesion making.

Prophet is a procedure for forecasting time series data based on an additive model where non-linear trends are fit with yearly, weekly, and daily seasonality, plus holiday effects. [Prophet](https://research.fb.com/prophet-forecasting-at-scale/).

### Where best used.

Because  prophet is a procedure it doesn't work in all types of data.
Prophet shine in  business data that contains the following values:
 
 >. Hourly, daily, or weekly observations with at least a few months (preferably a year) of history

 > . Important holidays that occur at irregular intervals that are known in advance (e.g. Madaraka day).

 >. Trends that are non-linear growth curves, where a trend hits a natural limit or saturates.


### How it works

>.A piecewise linear or logistic growth curve trend. Prophet automatically detects changes in trends by selecting changepoints from the data.

>. A yearly seasonal component modeled using Fourier series.

>. A weekly seasonal component using dummy variables.

>. A user-provided list of important holidays.

## Getting started in python 

### Installation 
Prophet is on PyPI, so you can use pip to install it:

```

pip install fbprophet

```

### Quick start

```python

# Python
import pandas as pd
from fbprophet import Prophet

df = pd.read_csv('../examples/example_wp_log_peyton_manning.csv')
df.head()


m = Prophet()
m.fit(df)

future = m.make_future_dataframe(periods=365)
future.tail()

forecast = m.predict(future)
forecast[['ds', 'yhat', 'yhat_lower', 'yhat_upper']].tail()

fig1 = m.plot(forecast)

```







