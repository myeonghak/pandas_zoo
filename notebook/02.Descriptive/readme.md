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


2. **열 별로 다양한 기술 통계량 확인하기 (Checking specific statistics from columns)**

<br/>  

##### [키워드 key words]  
  - 기술 통계량, 첨도, 왜도
  - descriptive statistics



##### FYI  
  - it excludes nan values automatically

``` python
panda_members = {'Name' : ['Ace', 'Baam', 'Choco', "Dill", "Eren", "Foo"],
                'Bamboo': [20, np.nan, 7, np.nan, np.nan, 20],
                'Water': [30, 40, 10, np.nan, 11, 20,]}


DF = pd.DataFrame.from_dict(panda_members)


DF.agg(
{"Bamboo": ["min", "max", "median", "skew"],
"Water": ["min", "max", "median", "skew"]}
)

```


![describe](/assets/02.Descriptive/statistics_agg.png)  


3. **열 내의 유니크한 카테고리 별로 개수/비율 구하기  (Counting numbers of sample / Calculting proportion per category in a column)**


<br/>  


``` python
panda_members = {'Name' : ['Ace','Ace', 'Baam','Ace', 'Choco','Baam','Choco', 'Ace'],
                'Bamboo': [20, 20, 10, 15, 100,10 , 100, 15],
                 'Hobby' : ['Rolling', 'Rolling', 'Playing Dead', "Playing Dead", "Sleeping",'Playing Dead', "Rolling",'Sleeping']}

DF = pd.DataFrame.from_dict(panda_members)

DF.Hobby.value_counts()
```
![describe](/assets/02.Descriptive/value_counts.png)  
``` python
DF.Hobby.value_counts(normalize=True)

```
![describe](/assets/02.Descriptive/value_counts_ratio.png)  
