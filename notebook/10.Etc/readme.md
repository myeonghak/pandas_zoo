### 10. etc  
--------




1. **출력 결과 확장하기 (expanding pandas output to be shown)**  


<br/>  


##### [키워드 key words]  
  - 출력, 확대, 확장, 열 수, 칼럼 수, 행 수
  - expanding, output, result, print


```python
# daily bamboo and water consumption in pandas zoo
panda_members = {'Name' : ['Ace', 'Baam', 'Choco', "Dill", "Eren", "Foo"],
                'Bamboo': [20.12345678, np.nan, 7, np.nan, np.nan, 20.12345678],
                'Water': [30.12345678, 40, 10, np.nan, 11, 20],
                'Very_Cute': [True, False, True, True, True, True]}

DF = pd.DataFrame.from_dict(panda_members)

# 출력할 최대 행 갯수를 5로 설정 // maximum number of rows to show
pd.set_option("display.max_rows", 5)
# 출력할 최대 열 갯수를 3개로 설정 // maximum number of cols to show
pd.set_option("display.max_columns", 3)
# 출력할 float의 소숫점 자릿수 제한 // maximum digits to show below decimal point
pd.set_option("display.float_format", lambda x : "%.2f" %x)

DF

```

![expand_output_original](/assets/10.Etc/expand_output_original.png)  

- let's expand the output
- 출력을 다시 늘려 줍니다. 위 메서드의 argument를 수정하면 됩니다.

```python
# 출력할 최대 행 갯수를 5로 설정 // maximum number of rows to show
pd.set_option("display.max_rows", 200)
# 출력할 최대 열 갯수를 3개로 설정 // maximum number of cols to show
pd.set_option("display.max_columns", 200)
# 출력할 float의 소숫점 자릿수 제한 // maximum digits to show below decimal point
pd.set_option("display.float_format", lambda x : "%.10f" %x)

DF
```



![expand_output_exp](/assets/10.Etc/expand_output_exp.png)  
