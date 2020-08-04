# Sunday_Project
Aboyeji_Solution

This is code for stage B work on Hamoye
#import data
import pandas as pd
df = pd.read_csv('Data/energydata_complete.csv')

#import linear model 
from sklearn import linear_model
reg = linear_model.LinearRegression()
# drop date and light
df_n = df.drop(columns = ['date', 'lights'])
#normalization
from sklearn.preprocessing import MinMaxScaler
scaler = MinMaxScaler()
normalize_dfn = pd.DataFrame(scaler.fit_transform(df_n), columns = df_n.columns)
# y and x variables 
x = normalize_dfn.T2
y = normalize_dfn.T6
# train model
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test = train_test_split(x, y, test_size = 0.2, random_state =42)
reg.fit(x_train.values.reshape(-1,1), y_train)
#predicted values 
import numpy as np
predicted_values = reg.predict(np.array([x_test]).reshape( 3947, 1))
# Mean absolute error
from sklearn.metrics import mean_absolute_error
mae = mean_absolute_error(y_test, predicted_values)
round(mae, 2)
# r2 value
from sklearn.metrics import r2_score
r2_scor = r2_score(y_test, predicted_values)
round(r2_scor, 2)
# rss
import numpy as np
rss = np.sum(np.square(y_test - predicted_values))
round(rss, 2)
# mean sqaure error
from sklearn.metrics import mean_squared_error
rmse = np.sqrt(mean_squared_error(y_test, predicted_values))
round(rmse, 2)
