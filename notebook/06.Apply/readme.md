### 6. Apply  
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




2. **문자열 행에서 마지막 n개 단어 취하기 (getting last n characters from a string column)**  


<br/>  


```python

panda_members = {'Hobby' : ['Rolling', 'Sleeping', 'Playing Dead', "Playing Dead", "Sleeping", "Rolling", "Eating","Playing Dead"],
                 'Age': [20, 20, 11, 12, 12, 11, 11, 12],
                'Name': ["Ace","Ace","Choco","Baam","Baam","Choco","Choco","Baam"]}

DF = pd.DataFrame.from_dict(panda_members)

# get last 3 chars from Hobby column
DF.Hobby.str[-3:]
DF.Hobby.apply(lambda x: x[-3:]) # these two codes return same output

```

![apply_lambda](/assets/06.Apply/last_n_word.png)  



<br/>  




3. **열에 if else 조건문 적용하기 (applying if else statement to a column)**  


<br/>  

```python
panda_members = {'Name' : ['Ace','Ace', 'Baam','Ace', 'Choco','Baam','Choco', 'Ace'],
                'Bamboo': [20, 20, 10, 15, 100,10 , 100, 15],
                 'Hobby' : ['Rolling', 'Rolling', 'Playing Dead', "Playing Dead", "Sleeping",'Playing Dead', "Rolling",'Sleeping']}

DF = pd.DataFrame.from_dict(panda_members)

DF.Bamboo.where(lambda x: x>10, other=0)
```

![apply_lambda](/assets/06.Apply/pd_where.png)  



<br/>  





4. **apply에 여러개 인자 넣어주기 (multiple argument for apply statement in DF)**  


<br/>  


```python

panda_members = {'Name' : ['Ace','Ace', 'Baam','Ace', 'Choco','Baam','Choco', 'Ace'],
                'Bamboo': [20, 20, 10, 15, 100,10 , 100, 15],
                 'Hobby' : ['Rolling', 'Rolling', 'Playing Dead', "Playing Dead", "Sleeping",'Playing Dead', "Rolling",'Sleeping']}

DF = pd.DataFrame.from_dict(panda_members)

def check_if_between(x,from_,to_):
    if x > from_ and x < to_:
        return "YES!"
    else:
        return "NO!!"

# YES means that panda's Bamboo consumption amount is between 5 and 20
DF.Bamboo.apply(check_if_between, args=(5, 20))


```

![apply_lambda](/assets/06.Apply/apply_multiple_args.png)  



<br/>  
