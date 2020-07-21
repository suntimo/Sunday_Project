# Sunday_Project
Aboyeji_Solution

This is code for stage A work on Hamoye

#Solution to Q1
A = [1,2,3,4,5,6]
B = [13, 21, 34]
A_B = A.extend(B)
print(A)
print(A_B)

#solution to Q2
import numpy as np
np.identity(3)

#solution to Q4
data_work['fuel_mmbtu_per_unit'].describe()

# solution to Q5
skewness = data_work['fuel_qty_burned'].skew()
kurtosis = data_work['fuel_qty_burned'].kurtosis()
print(skewness)
print(kurtosis)

 # SOLUTION TO Q 6
missing_feature = data_work.isnull().sum()
count = data_work['fuel_unit'].count()
percent = missing_feature/count *100

print(missing_feature)
print(percent)

# solution to question 9
coal_data = data_work['fuel_type_code_pudl'] =='coal'
coal_data.head()
