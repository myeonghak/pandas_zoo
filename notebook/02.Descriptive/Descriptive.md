### 2. Descriptive  
--------


1. **기술 통계량 조회하기 (Getting desriptive statistics from dataframe)**  
<br/>  

##### [키워드 key words]  
  - 샘플 수, 평균, 표준편차, 4분위수 (최솟값/ 25%/ 50%/ 75%/ 최댓값), 기술 통계량, 요약
  - count, mean, median, std, standard deviation, variance, description, summary
  - statistics, 4-quantile, 4th quantile, quartile


##### FYI  
  - it excludes nan values automatically

``` python
panda_members = {'Name' : ['Ace', 'Baam', 'Choco'],
                'Bamboo': [20, 12, 7],
                'Water': [30, 40, 10]}


DF = pd.DataFrame.from_dict(panda_members)

DF.describe()
```


![describe](/assets/02.Descriptive/describe.png)  
