### 3. Imputation - Missing values
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



2. **결측 포함된 행/열 날리기 (Droping rows/cols with NA values)**


<br/>  


##### [키워드 key words]  
  - 결측값, 버리기, 제거, 삭제,
  - dropna, drop rows, subset

```python


panda_members = {'Name' : ['Ace', 'Baam', 'Choco', "Dill", "Eren", "Foo"],
                'Bamboo': [20, np.nan, 7, np.nan, np.nan, 20],
                'Water': [30, 40, 10, np.nan, 11, 20,]}


DF = pd.DataFrame.from_dict(panda_members)

DF
```

![count_nan](/assets/03.Imputation/dropna_orig.png)  

```python
# drop rows with more than one na value
DF.dropna()
```
![count_nan](/assets/03.Imputation/dropna_after.png)  
```python
# drop rows that contains NA value in "Water" column
DF.dropna(subset=["Water"])

```
![count_nan](/assets/03.Imputation/dropna_subset.png)  



<br/>  
