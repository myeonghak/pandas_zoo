


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

1.	[데이터 프레임 DataFrame](#dataframe)
2.	[조회하기 Descriptive](#descriptive)
3.	[결측치 처리 Missing Values and Imputation](#imputation)
4.	[행/열에 조건 걸기 Filter](#filter)
5.	[인덱싱 Indexing](#indexing)
6.	[함수 적용하기 Apply a Function](#apply)
7.  [그룹별 조작하기 Groupby / Aggregating](#groupby)
8.	[시계열 Time Series](#time-series)
9.	[시각화 Plot](#plot)  
10.	[기타 Etc](#etc)  



<br/>  

<a id="dataframe"></a>
### 1. 데이터 프레임 만들기 Create and Load  [click here!](/notebook/01.DataFrame)
--------

1.  **리스트로 새로운 데이터프레임 만들기 (Creating new DataFrame from lists)**  

2. **딕셔너리로 새로운 데이터 프레임 만들기 (Creating new DataFrame from dict of lists)**  

3. **복수의 데이터 프레임 병합하기 (merging multiple(more than 2) DataFrames)**

4. **기존의 데이터프레임에 새로운 행 추가하기 (Appending a new row to an existing DataFrame)**

5. **새로운 열을 추가하지 않고 기존의 열에 새로운 값을 병합하기 (replacing columns using existing DF)**  
pd.update

<br/>  




<a id="descriptive"></a>
### 2. 조회하기 Descriptive    [click here!](/notebook/02.Descriptive)
--------


1. **기술 통계량 조회하기 (Getting desriptive statistics from dataframe)**  
2. **열 별로 다양한 기술 통계량 확인하기 (Checking specific statistics from columns)**
3. **열 내의 유니크한 카테고리 별로 개수/비율 구하기  (Counting numbers of sample / Calculting proportion per category in a column)**


<br/>  

<a id="imputation"></a>
### 3. 결측치 처리 Missing Values and Imputation   [click here!](/notebook/03.Missing_Values_and_Imputation)
--------
1. **열 별로 결측치가 포함된 레코드의 수 세기 (Determining the number of NA values in columns)**  

2. **결측 포함된 행/열 날리기 (Droping rows/cols with NA values)**
pd.dropna


<br/>  


<a id="filter"></a>
### 4.행/열에 조건 걸기 Filter  [click here!](/notebook/04.Filter)
--------

1. **특정 단어를 포함한 row만 골라내기 (Getting rows that contain specific text/word/string)**  
pd.Series.str.contains   


2. **데이터프레임 열(시리즈) 내에서 리스트 내의 특정 값이 있는 행 골라내기 (Using a list of values to select rows from Data Frame)**
pd.Series.isin  

3. **중복되는 행 제거하기, 열(복수 가능) 기준 혹은 전체 행 기준 (Droping duplicated/repeated/redundant rows, in respect to column(s) or full row)**
pd.drop_duplicates



<a id="indexing"></a>
### 5. 인덱싱 Indexing    [click here!](/notebook/05.Indexing)
--------



1. **loc로 새로운 칼럼 할당하기 (Assigning a new column using loc method)**  

2. **원하는 데이터 타입의 칼럼만 선택하기 (Selecting columns by specific data types)**  


<br/>  



<a id="apply"></a>
### 6. 함수 적용하기 Apply    [click here!](/notebook/06.Apply)
--------


1. **사용자 지정 함수 적용하기 (Applying lambda function to Pandas Series)**  
2. **문자열 행에서 마지막 n개 단어 취하기 (getting last n characters from a string column)**
3. **열에 if else 조건문 적용하기 (applying if else statement to a column)**
4. **apply에 여러개 인자 넣어주기 (multiple argument for apply statement in DF)**


<a id="groupby"></a>
### 7. 그룹별 조작하기 Groupby    [click here!](/notebook/07.Groupby)
--------

1. **그룹 별로 평균 값 구하기 (Getting average value of each column per group)**  


2. **그룹 별로 Multi level one-hot encoding 하기 (one-hot encoding for multi-level column data)**  

<br/>  


<a id="time-series"></a>
### 8. 시계열 Time Series    [click here!](/notebook/08.Time_Series)
--------


1. **행 별 차이 구하기, 차분 (Getting difference between rows)**  

<br/>  


<a id="plot"></a>
### 9. 시각화 Plot    [click here!](/notebook/09.Plot)
--------

1. **판다스 시리즈 데이터 시각화하기 (Drawing a quick plot using pandas series)**  


<a id="etc"></a>
### 10. 기타 etc    [click here!](/notebook/10.Etc)
--------

1. **출력 결과 확장하기 (Expanding pandas output to be shown)**  
