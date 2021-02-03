### 5. Indexing  
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
