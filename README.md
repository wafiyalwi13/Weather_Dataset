# Weather_Dataset
Using Numpy from Python Libraries to aggregate, calculate and summarize the weather data 

## Asking Question
From the dataset - we want to seek for the following question;

1. Find all the unique 'Wind Speed' values in the data.
2. Find the number of times when the 'Weather is exactly clear'
3. Find the number of times when 'Wind Speed was exactly 4km/h'
4. Find out all the null values in the data
5. Rename the column name 'Weather' of the dataframe to 'Weather Condition'
6. What is the mean 'Visibilty'
7. What is the Standard Deviation of 'Pressure' in this data?
8. What is the Variance of 'Relative Humidity' in this data ?
9. Find all instances when 'Snow' was recorded
10. Find all instance when 'Wind Speed is above 24' and 'Visibility is 25'
 
## Data Wrangling
Data wrangling is the process of converting raw data into a usable form. We will prepare the data to fit into Python - Jupyter Notebook

## Preparing the data


```
#import libraries

import pandas as pd
import numpy as np

#import csv
data = pd.read_csv(r "c/User/WafiyAlwi/DataAnalytics/ProjectsTrial " )
```

## Q1 : Find all the unique 'Wind Speed' values in the data.

```
data.head(2)
data.nunique() <---- no of unique value
data['Wind Speed_km/h'].unique()
```

## Q2 : Find the number of times when the 'Weather is exactly clear'

```
#value_counts()
data.Weather.value_counts()

#filtering 
data.head(2)
data.Weather == 'Clear'

#groupby()
data.head(2)
data.groupby('Weather').get_group('Clear')  #get function to get particular element from the column

```

## Q3 : Find the number of times when 'Wind Speed was exactly 4km/h'

```
data['Wind Speed_km/h'] == 4         #using this queries only gives you Boolean data types/format
data[data['Wind Speed_km/h'} == 4 ]  #use data[xxxx] to get all the value required
```

## Q4 :  Find out all the null values in the data
 ```
data_isnull().sum()
data_notnumm().sim()
```

## Q5 : Rename the column name 'Weather' of the dataframe to 'Weather Condition'

```
data.rename(columns = {'Weather' : ' Weather Conditions'})  --> this only for this query only

data.rename(columns = {'Weather : 'Weather Conditions'}, inplace = True) --> permanently change
```

## Q6 : What is the mean 'Visibilty'

```
data.Visibility_km.mean()
```

## Q7 : What is the Standard Deviation of 'Pressure' in this data?
```
data.Press_kPa.std()
```

## Q8 : What is the Variance of 'Relative Humidity' in this data ?
```
data['Rel Hum_%].var()
```

## Q9 : Find all instances when 'Snow' was recorded 

```
#value_counts()
#data.head(2)

data['Weather Condition'].value_counts

#Filtering
data[data['Weather Condition'] == 'Snow']

#str.contains 
#all the words that contains the word 'Snow' eg : Snow Fog, Snow Drizzle

data[data['Weather Conditions'].str.contains('Sonw')]

data[data['Weather Conditions'].str.contains('Sonw')].head(50) --> 'Snow' in front of sentences 'Snow Fog'
data[data['Weather Conditions'].str.contains('Sonw')].tails(50) --> 'Snow' at the end of sentences 'Ice Snow'
```

## Q10 : Find all instance when 'Wind Speed is above 24' and 'Visibility is 25'
```
data[(data['Wind Speed_km/h']>24) & (data['Visibility_km']==25)]
```
 
