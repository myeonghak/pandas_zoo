### 1. DataFrame
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
![create_a_df](/assets/01.DataFrame/create_df.png)  


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
![create_a_df](/assets/01.DataFrame/create_df.png)  

<br/>  



3. **복수의 데이터 프레임 병합하기 (merging multiple(more than 2) DataFrames)**



<br/>  


##### [키워드 key words]  
  - 데이터프레임 병합, 줄줄이 붙이기
  - multiple DF, merge, concatenate



```python
panda_members = {'Name' : ['Ace', 'Baam', 'Choco'],
                'Bamboo': [20, 12, 7],
                'Water': [30, 40, 10]}

DF = pd.DataFrame.from_dict(panda_members)
# DF = pd.DataFrame.from_dict(panda_members)

# make a list of DF objects
DF_list=[DF,DF,DF]

from functools import reduce

reduce(lambda left,right: pd.merge(left,right,left_index=True,right_index=True), DF_list )

```
![create_a_df](/assets/01.DataFrame/multiple_dfs.png)  

or you can simply use `pd.concat`
```python
pd.concat(DF_list,axis=1)
```


<br/>  
