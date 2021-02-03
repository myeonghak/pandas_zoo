### 8. Time Series  
--------


1. **행 별 차이 구하기, 차분 (get difference between rows)**  
<br/>  


##### [키워드 key words]  
  - 행별, 차이, 차분, 이동, 시계열
  - by row, difference, gap, between, time series

```python

# daily bamboo and water consumption in pandas zoo
panda_consumption = {'Day' : [1, 2, 3, 4, 5, 6],
                'Cum_Bamboo': [20, 30, 60, 100, 120, 150],
                'Cum_Water': [15, 30, 45, 70, 90, 120],
                }

# make dataframe
DF = pd.DataFrame.from_dict(panda_consumption)

# get difference between daily consumption of Bamboo
DF["Cum_Bamboo"].diff()

# or

DF["Cum_Bamboo"]-DF["Cum_Bamboo"].shift(1)

```


![diff_bamboo](/assets/08.Time_Series/diff_bamboo.png)  




<br/>  
