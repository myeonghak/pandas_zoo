### 1. Create and Load
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
