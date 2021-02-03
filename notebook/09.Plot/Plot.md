### 9. Plot  
--------




1. **판다스 시리즈 데이터 시각화하기 (draw a quick plot using pandas series)**  


<br/>  


##### [키워드 key words]  
  - 시각화, 그림, 도식화, 그리기, 시리즈
  - series, plot, draw, visualization


```python
# daily bamboo and water consumption in pandas zoo

panda_consumption = {'Day' : [1, 2, 3, 4, 5, 6],
                'Cum_Bamboo': [20, 30, 60, 100, 120, 150],
                'Cum_Water': [15, 30, 45, 70, 90, 120],
                }

# make dataframe
DF = pd.DataFrame.from_dict(panda_consumption)

# draw a plot
DF.Cum_Bamboo.plot()

```

![series_plot](/assets/09.Plot/series_plot.png)  
