### 6. Apply  
--------


1. **사용자 지정 함수 적용하기 (apply lambda function to Pandas Series)**  


<br/>  


##### [키워드 key words]  
  - 람다, 함수, 맵핑
  - apply, mapping, custom function, column

```python

# daily bamboo and water consumption in pandas zoo

panda_consumption = {'Day' : [1, 2, 3, 4, 5, 6],
                'Cum_Bamboo': [20, 30, 60, 100, 120, 150],
                'Cum_Water': [15, 30, 45, 70, 90, 120],
                }

# make dataframe
DF = pd.DataFrame.from_dict(panda_consumption)

# add 50 to every consumption of Water
DF.Cum_Water.apply(lambda x: x+50)

```

![apply_lambda](/assets/06.Apply/apply_lambda.png)  



<br/>  
