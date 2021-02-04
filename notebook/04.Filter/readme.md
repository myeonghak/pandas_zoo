### 4. Filter


1. **특정 단어를 포함한 row만 골라내기 (get rows that contain specific text/word/string)**  


<br/>  


##### [키워드 key words]  
  - 특정 단어, 텍스트, 스트링
  - string, test, word, select, filter, specific


```python
# panda members info
panda_members = {'Name' : ['Ace', 'Baam', 'Choco', "Dill", "Eren", "Foo"],
                'Bamboo': [20, np.nan, 7, np.nan, np.nan, 20],
                'Water': [30, 40, 10, np.nan, 11, 20,],
                'Emotion': ["Happy","Very Happy","Sad","Happy after lunch","So so","Very Happy"]}


DF = pd.DataFrame.from_dict(panda_members)

# using str.contains method, filter out rows with text "Happy"
DF[DF.Emotion.str.contains("Happy")]

```


![assign_col](/assets/04.Filter/filter_specific_word.png)  


<br/>  


2. **데이터프레임 열(시리즈) 내에서 리스트 내의 특정 값이 있는 행 골라내기 (Using a list of values to select rows from Data Frame)**



<br/>  


##### [키워드 key words]  
  - 리스트 조건, 배열, 특정 값, 행 골라내기
  - list, condition, check


```python
# panda members info
panda_members = {'Name' : ['Ace', 'Baam', 'Choco', "Dill", "Eren", "Foo"],
                'Bamboo': [20, np.nan, 7, np.nan, np.nan, 20],
                'Water': [30, 40, 10, np.nan, 11, 20,],
                 'Hobby' : ['Rolling', 'Sleeping', 'Playing Dead', "Playing Dead", "Sleeping", "Rolling"]}

DF = pd.DataFrame.from_dict(panda_members)

# I want to see pandas with only these two hobbies
list_to_check=['Rolling','Sleeping']

DF[DF.Hobby.isin(list_to_check)]

```


![assign_col](/assets/04.Filter/pd_isin.png)  


<br/>  
