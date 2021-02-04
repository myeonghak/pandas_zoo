### 7. Groupby  
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
