# IMPORT LIBRARIES
import numpy as np
import pandas as pd
import scipy.stats
from matplotlib import pyplot 

# CREATE LISTS
csv_lst=      [ 37, 	 24, 	 81, 	 26, 	 22, 	 14 ,	 51 	, 17 ,	 42 	, 15 	, 37 	, 84 	, 36 	, 38 	, 38 ,	 15 ]
parquet_lst = [ 36 ,	 23 ,	 83 	, 21 	, 23 ,	 23 ,	 35 	, 20 ,	 37 ,	 16 ,	 16 ,	 78 ,	 40 ,	 16 	, 33 ,	 17 ]

#CONVERT LISTS TO DATAFRAME
csv_df = pd.DataFrame(csv_lst)
parquet_df = pd.DataFrame(parquet_lst)

#LOOK STATISTICAL VALUES
csv_df.describe()
parquet_df.describe()

#CREATE HISTOGRAM TO SEE THE DISTRIBUTION
pyplot.hist(csv_df)
pyplot.hist(parquet_df)

#NORMALITY TEST 
# Shapiro-Wilk Test 
from scipy.stats import shapiro
# for csv
stat, p = shapiro(csv_df)
print('Statistics=%.3f, p=%.3f' % (stat, p))
# interpret results
alpha = 0.05
if p > alpha:
    print('Sample looks Gaussian (fail to reject H0)')
else:
    print('Sample does not look Gaussian (reject H0)')

# for parquet
stat, p = shapiro(parquet_df)
print('Statistics=%.3f, p=%.3f' % (stat, p))
# interpret results
alpha = 0.05
if p > alpha:
    print('Sample looks Gaussian (fail to reject H0)')
else:
    print('Sample does not look Gaussian (reject H0)')


# HYPOTHESIS TEST FOR NON-NORMAL DISTRIBUTIONS
from scipy.stats import mannwhitneyu 
# perform mann whitney test 
stat, p_value = mannwhitneyu(csv_df, parquet_df) 
print('Statistics=%.2f, p=%.2f' % (stat, p_value)) 
# Level of significance 
alpha = 0.05
# conclusion 
if p_value < alpha: 
    print('Reject Null Hypothesis (Significant difference between two samples)') 
else: 
    print('Do not Reject Null Hypothesis (No significant difference between two samples)')
