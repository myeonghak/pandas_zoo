


Pandas Zoo
==============================================




<p align="center"> <img src="/assets/readme/pandas_zoo.jpg" alt="drawing" width="200"/>

<p align="center"> <img src="/assets/readme/pandas_official.png" alt="drawing" width="100"/>


:panda_face: A zoo for [pandas](https://pandas.pydata.org/)  methods, functions, usages! :panda_face:

Search for any feature you need by key words.

A short code snippet will be attached to the features so you can easily apply it to your work.

before copy & paste the snippet, make sure you imported packages as below.

```python
import pandas as pd
import numpy as np
```

판다스의 다양한 기능을 소개하는 repo 입니다!

원하는 기능을 바로 찾아 쓸 수 있도록 정리할 예정입니다.

사용하고자 하는 목적에 맞게 바로 적용할 수 있도록, 코드 스니펫을 첨부합니다.

코드 복붙 전에, 판다스와 넘파이를 잘 호출 하셨는지 확인해 주세요.




<br/>  

Contents
--------

1.	[Create / Load DataFrame](#create-and-load)
2.	[Descriptive](#descriptive)
3.	[Imputation](#imputation)
4.	[Groupby / Aggregating](#groupby)
5.	[Time Series](#time-series)
6.	[Apply a Function](#apply)
7.	[Indexing](#indexing)
8.	[Plot](#plot)  
9.	[Etc](#etc)  



<br/>  

### Create and Load
--------

1.  **리스트로 새로운 데이터프레임 만들기 (Creating new DataFrame from lists)**  

<br/>  

##### [키워드 key words]  
  - list, create, dataframe, make, DF
  - 리스트, 데이터프레임, 만들기

```python

panda_members = [['Ace', 20, 30], ['Baam', 12, 40], ['Choco', 7, 10]]

DF = pd.DataFrame(panda_members, columns = ['Name', 'Bamboo' ,'Water'])

DF

```
![create_a_df](/assets/01.Create_and_Load/create_df.png)  


<br/>  



2. **딕셔너리로 새로운 데이터 프레임 만들기 (Creating new DataFrame from dict of lists)**  


<br/>  


##### [키워드 key words]  
  - dict, dictionary, create, dataframe, make, DF
  - 딕셔너리, 사전, 데이터프레임, 만들기

##### FYI  
  - you have to make value part in a form of list, not integer or float.


```python

panda_members = {'Name' : ['Ace', 'Baam', 'Choco'],
                'Bamboo': [20, 12, 7],
                'Water': [30, 40, 10]}


DF = pd.DataFrame(panda_members)
# DF = pd.DataFrame.from_dict(panda_members)

DF
```
![create_a_df](/assets/01.Create_and_Load/create_df.png)  

<br/>  

### Descriptive  
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

<br/>  

### Imputation  
--------
1. **열 별로 결측치가 포함된 레코드의 수 세기 (Determining the number of NA values in columns)**  


<br/>  


##### [키워드 key words]  
  - 결측값 세기, 결측치, nan값, 칼럼, 피처
  - nan, na, invalid values, column, feature

```python
panda_members = {'Name' : ['Ace', 'Baam', 'Choco', "Dill", "Eren", "Foo"],
                'Bamboo': [20, np.nan, 7, np.nan, np.nan, 20],
                'Water': [30, 40, 10, np.nan, 11, 20,]}


DF = pd.DataFrame.from_dict(panda_members)

DF.isna().sum()
```

![count_nan](/assets/03.Imputation/count_nan.png)  


<br/>  


### Groupby  
--------

1. **그룹 별로 평균 값 구하기 (get average value of each column per group)**  


<br/>  


##### [키워드 key words]  
  - 그룹, 집단 별, 묶음, 평균, 그룹바이
  - groupby, mean, average, by group


```python

# get average Bamboo and Water consumption per group
panda_members = {'Name' : ['Ace', 'Baam', 'Choco', "Dill", "Eren", "Foo"],
                'Bamboo': [20, 11, 7, 12, 12, 20],
                'Water': [30, 40, 10, 32, 11, 20],
                'Class': ["A","A","C","B","B","C"]}

# make dataframe
DF = pd.DataFrame.from_dict(panda_members)

# define a categorical feature to make a group with
DF.groupby("Class").mean()

```

![groupby_mean](/assets/07.Groupby/groupby_mean.png)  

<br/>  


2. **그룹 별로 Multi level one-hot encoding 하기 (one-hot encoding for multi-level column data)**  

<br/>   


특정 그룹이 포함하는 모든 범주형 변수에 대해 1로 one-hot을 표시합니다.

get columns of binary value that represents yes or no for categorical value of each group.  


<br/>  


##### [키워드 key words]  
  - 멀티 핫, 멀티 레벨, 원 핫, 원핫 인코딩
  - milti-hot, multi-level, multi class one-hot encoding


```python

# records of hobbies of pandas
panda_members = {'Hobby' : ['Rolling', 'Sleeping', 'Playing Dead', "Playing Dead", "Sleeping", "Rolling", "Eating","Playing Dead"],
                 'Age': [20, 20, 11, 12, 12, 11, 11, 12],
                'Name': ["Ace","Ace","Choco","Baam","Baam","Choco","Choco","Baam"]}

DF = pd.DataFrame.from_dict(panda_members)

# multi level one-hot encoding
DF[["Name"]].join(pd.get_dummies(DF.Hobby).add_prefix("Hobbies_of_pandas_")).groupby("Name").max()


```


- 우리 Ace는 굴러다니기와 잠자기라는 취미를 가지고 있네요.  
- the result shows that Ace's hobby is to roll and sleep.   




![multi_one_hot](/assets/07.Groupby/multi_one_hot.png)  

<br/>  


### Time Series  
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


### Apply  
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


### Indexing  
--------



1. **loc로 새로운 칼럼 할당하기 (Assign a new column using loc method)**  


<br/>  


##### [키워드 key words]  
  - 라벨 기반 인덱싱, 칼럼 할당하기, 열 생성하기
  - loc, label-based indexing, assign a column, create a column


```python
# panda members info
panda_members = {'Name' : ['Ace', 'Baam', 'Choco', "Dill", "Eren", "Foo"],
                'Bamboo': [20, np.nan, 7, np.nan, np.nan, 20],
                'Water': [30, 40, 10, np.nan, 11, 20,]}


DF = pd.DataFrame.from_dict(panda_members)

# assign Age column, with a value of 10
DF.loc[:,"Age"]=10

# show df
DF

```


![assign_col](/assets/05.Indexing/assign_col.png)  


<br/>  




2. **원하는 데이터 타입의 칼럼만 선택하기 (Selecting columns by specific data types)**  


<br/>  


##### [키워드 key words]  
  - 열 선택, 칼럼 선택, 자료형, 데이터 타입, 원하는 칼럼, 오브젝트, 문자열, 수치형, 날짜
  - dtype, select column, select by dtype, object, numeric, datetime


```python
# panda members info
panda_members = {'Name' : ['Ace', 'Baam', 'Choco', "Dill", "Eren", "Foo"], # object
                'Bamboo': [20, np.nan, 7, np.nan, np.nan, 20], # int
                'Water': [30, 40, 10, np.nan, 11, 20,], # int
                'Very_Cute': [True, False, True, True, True, True]} # bool

DF = pd.DataFrame.from_dict(panda_members)

# default argument is include. if you don't specify arg name, it returns columns "with" specific dtype.

# DF.select_dtypes("O")
DF.select_dtypes(include="O")

```


- 오브젝트 자료형을 가진 칼럼만 포함한 데이터 프레임을 출력해 줍니다.    
- returns dataframe only object dtype columns.   



![assign_col](/assets/05.Indexing/select_dtype_include.png)  




``` python
# exclude columns with object dtype
DF.select_dtypes(exclude="O")

```

- 오브젝트 자료형이 아닌 칼럼만 포함한 데이터 프레임을 출력해 줍니다.  
- returns dataframe without object dtype columns.  


![assign_col](/assets/05.Indexing/select_dtype_exclude.png)  

<br/>  



### Plot  
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



### etc  
--------




1. **출력 결과 확장하기 (expanding pandas output to be shown)**  


<br/>  


##### [키워드 key words]  
  - 출력, 확대, 확장, 열 수, 칼럼 수, 행 수
  - expanding, output, result, print


```python
# daily bamboo and water consumption in pandas zoo
panda_members = {'Name' : ['Ace', 'Baam', 'Choco', "Dill", "Eren", "Foo"],
                'Bamboo': [20.12345678, np.nan, 7, np.nan, np.nan, 20.12345678],
                'Water': [30.12345678, 40, 10, np.nan, 11, 20],
                'Very_Cute': [True, False, True, True, True, True]}

DF = pd.DataFrame.from_dict(panda_members)

# 출력할 최대 행 갯수를 5로 설정 // maximum number of rows to show
pd.set_option("display.max_rows", 5)
# 출력할 최대 열 갯수를 3개로 설정 // maximum number of cols to show
pd.set_option("display.max_columns", 3)
# 출력할 float의 소숫점 자릿수 제한 // maximum digits to show below decimal point
pd.set_option("display.float_format", lambda x : "%.2f" %x)

DF

```

![expand_output_original](/assets/10.Etc/expand_output_original.png)  

- let's expand the output
- 출력을 다시 늘려 줍니다. 위 메서드의 argument를 수정하면 됩니다.

```python
# 출력할 최대 행 갯수를 5로 설정 // maximum number of rows to show
pd.set_option("display.max_rows", 200)
# 출력할 최대 열 갯수를 3개로 설정 // maximum number of cols to show
pd.set_option("display.max_columns", 200)
# 출력할 float의 소숫점 자릿수 제한 // maximum digits to show below decimal point
pd.set_option("display.float_format", lambda x : "%.10f" %x)

DF
```



![expand_output_exp](/assets/10.Etc/expand_output_exp.png)  
