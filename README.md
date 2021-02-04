


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

Example  
-------

1. **사용자 지정 함수 적용하기 (Applying lambda function to Pandas Series)**  

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


<center><img src="/assets/06.Apply/apply_lambda.png" align="center" alt="drawing" width="200"/></center>  


<br/>  

Contents
--------

1.	[Create / Load DataFrame](#create-and-load)
2.	[Descriptive](#descriptive)
3.	[Imputation](#imputation)
4.	[Filter](#filter)
5.	[Indexing](#indexing)
6.	[Apply a Function](#apply)
7.  [Groupby / Aggregating](#groupby)
8.	[Time Series](#time-series)
9.	[Plot](#plot)  
10.	[Etc](#etc)  



<br/>  

<a id="create-and-load"></a>
### 1. Create and Load  [click here!](/notebook/01.Create_and_Load)
--------

1.  **리스트로 새로운 데이터프레임 만들기 (Creating new DataFrame from lists)**  

2. **딕셔너리로 새로운 데이터 프레임 만들기 (Creating new DataFrame from dict of lists)**  


<br/>  




<a id="descriptive"></a>
### 2. Descriptive    [click here!](/notebook/02.Descriptive)
--------


1. **기술 통계량 조회하기 (Getting desriptive statistics from dataframe)**  
<br/>  

<a id="imputation"></a>
### 3. Imputation - Missing values   [click here!](/notebook/03.Imputation)
--------
1. **열 별로 결측치가 포함된 레코드의 수 세기 (Determining the number of NA values in columns)**  


<br/>  


<a id="filter"></a>
### 4. Filter  [click here!](/notebook/04.Filter)
--------

1. **특정 단어를 포함한 row만 골라내기 (Getting rows that contain specific text/word/string)**  
pd.Series.str.contains   


2. **데이터프레임 열(시리즈) 내에서 리스트 내의 특정 값이 있는 행 골라내기 (Using a list of values to select rows from Data Frame)**
pd.Series.isin  

3. **중복되는 행 제거하기, 열(복수 가능) 기준 혹은 전체 행 기준 (Droping duplicated/repeated/redundant rows, in respect to column(s) or full row)**
pd.drop_duplicates



<a id="indexing"></a>
### 5. Indexing    [click here!](/notebook/05.Indexing)
--------



1. **loc로 새로운 칼럼 할당하기 (Assigning a new column using loc method)**  

2. **원하는 데이터 타입의 칼럼만 선택하기 (Selecting columns by specific data types)**  


<br/>  



<a id="apply"></a>
### 6. Apply    [click here!](/notebook/06.Apply)
--------


1. **사용자 지정 함수 적용하기 (Applying lambda function to Pandas Series)**  


<a id="groupby"></a>
### 7. Groupby    [click here!](/notebook/07.Groupby)
--------

1. **그룹 별로 평균 값 구하기 (Getting average value of each column per group)**  


2. **그룹 별로 Multi level one-hot encoding 하기 (one-hot encoding for multi-level column data)**  

<br/>  


<a id="time-series"></a>
### 8. Time Series    [click here!](/notebook/08.Time_Series)
--------


1. **행 별 차이 구하기, 차분 (Getting difference between rows)**  

<br/>  


<a id="plot"></a>
### 9. Plot    [click here!](/notebook/09.Plot)
--------

1. **판다스 시리즈 데이터 시각화하기 (Drawing a quick plot using pandas series)**  


<a id="etc"></a>
### 10. etc    [click here!](/notebook/10.Etc)
--------

1. **출력 결과 확장하기 (Expanding pandas output to be shown)**  
