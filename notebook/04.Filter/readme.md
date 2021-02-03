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
