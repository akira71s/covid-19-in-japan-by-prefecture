# A Pyhton project: Correlationship between population & #positive COVID-19 cases in Japan by prefecture

![image](https://user-images.githubusercontent.com/40524432/194751564-6671d26d-00aa-416a-bbd8-d98c242c08cb.png)

## COVID-19 cases in Japan by prefecture (47prefectures)

In this project, I'm going to analyze the correlationship between population (& population density) and the
number of positive COVID-19 cases in Japan, by prefecture. (Japan has 47 prefectures.Tokyo is one of them.)
I will only focus on the total COVID-19 patients by prefecture, not on changes in the trend at daily or weekly
basis.

## Data source
Source: ./covid-19-japan-2022-01-04.csv
The csv file can be downloaded from https://www.stopcovid19.jp/tableview.html.
This is a portal website for COVID-19 run by the Japanese governmental organization.
There is no potential for personally identifiable distinctions as it only contains data 'by prefecture'.

## Data modification
By passing "thousands=','" parameters, I will treat "npopulation" & "area" columns as int64 (the original not
string object) so that they can be easily sorted for analysis. Also, even though the csv file has columns for #
deaths or # current patients (who are not recovered yet), I will not focus on those data.

```Python
# import modules
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
# read the csv file
df = pd.read_csv(
'./covid-19-japan-2022-01-04.csv',
thousands=',',
usecols=['name', 'ntotalpatients', 'npopulation', 'areainkm^2'])
```
