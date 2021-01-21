---
layout: posts
title: (ML) 데이터 전처리
comments: true
tags:
- Machine Learning
---





데이터 전처리란 수집한 데이터를 분석에 적합한 형태로 만드는 과정입니다.  
머신러닝 알고리즘의 학습 결과는 데이터의 품질이 결정하기에, 데이터를 올바르게 가공하는 작업은 대단히 중요합니다.



### 1\. 누락 데이터 처리

누락 데이터는 NaN (Not a Number) 로 표시됩니다.  
누락 데이터가 많아지면 데이터의 품질이 떨어지게 되므로, 이를 제거, 치환하는 작업이 필요합니다.



#### 누락 데이터 확인



- `df.info()`

  각 열에 속하는 NaN이 아닌 값의 개수를 출력

  ```python
  df.info()
  
  '''
  <class 'pandas.core.frame.DataFrame'>
  RangeIndex: 891 entries, 0 to 890
  Data columns (total 15 columns):
   #   Column       Non-Null Count  Dtype   
  ---  ------       --------------  -----   
   0   survived     891 non-null    int64   
   1   pclass       891 non-null    int64   
   2   sex          891 non-null    object  
   3   age          714 non-null    float64 
   4   sibsp        891 non-null    int64   
   5   parch        891 non-null    int64   
   6   fare         891 non-null    float64 
   7   embarked     889 non-null    object  
   8   class        891 non-null    category
   9   who          891 non-null    object  
   10  adult_male   891 non-null    bool    
   11  deck         203 non-null    category
   12  embark_town  889 non-null    object  
   13  alive        891 non-null    object  
   14  alone        891 non-null    bool    
  dtypes: bool(2), category(2), float64(2), int64(4), object(5)
  memory usage: 80.6+ KB
  '''
  ```

  



- `value_counts(normalize=False, sort=True, ascending=False, bins=None, dropna=True)`

    특정 column/series의 값 별로 개수 카운트
    
    `dropna = False` => NaN 값을 같이 출력
    `dropna = True` => NaN 값을 제외란 유효한 데이터 개수 출력
    
    ```python
    # deck 열의 값들을 카운트
    nan_deck = df['deck'].value_counts(dropna=False)
    print(nan_deck)
    
    '''
    NaN    688
    C       59
    B       47
    D       33
    E       32
    A       15
    F       13
    G        4
    Name: deck, dtype: int64
    '''
    ```
    
    
    
    
    
- `df.isnull()`

    값이 결측값이면 True, 아니라면 False 를 리턴합니다. 

    ```python
    print(df.head().isnull())
    
    '''
    survived  pclass    sex    age  sibsp  parch   fare  embarked  class  \
    0     False   False  False  False  False  False  False     False  False   
    1     False   False  False  False  False  False  False     False  False   
    2     False   False  False  False  False  False  False     False  False   
    3     False   False  False  False  False  False  False     False  False   
    4     False   False  False  False  False  False  False     False  False   
    
         who  adult_male   deck  embark_town  alive  alone  
    0  False       False   True        False  False  False  
    1  False       False  False        False  False  False  
    2  False       False   True        False  False  False  
    3  False       False  False        False  False  False  
    4  False       False   True        False  False  False  '''
    ```

    



#### 누락 데이터 제거



* `df.dropna(axis=0, how='any', thresh=None, subset=None, inplace=False)`

  특정 열/행을 제거합니다. 

  * **열 삭제**  (axis = 1)

    ```python
    # NaN 값이 500개 이상인 열을 모두 삭제 (thresh = 500)
    
    df_thresh = df.dropna(axis=1, thresh=500)
    print(df_thresh.columns)
    
    '''
    Index(['survived', 'pclass', 'sex', 'age', 'sibsp', 'parch', 'fare',
           'embarked', 'class', 'who', 'adult_male', 'embark_town', 'alive',
           'alone'],
          dtype='object')
    '''
    ```

  * **행 삭제** (axis = 0)

    ```python
    # age 열에 나이 데이터가 없는 모든 행 삭제
    
    df_age = df.dropna(axis=0, subset=['age'], how='any')
    print(len(df_age))
    
    
    # 714
    ```



#### 누락 데이터 치환



* `df.fillna(value=None, method=None, axis=None, inplace=False)`

  원본 객체를 변경하기 위해 `inplace = True` 추가

  

  ```python
  # age 열의 첫 10개 데이터 출력
  print(df['age'].head(10))
  print('\n')
  
  # age 열의 NaN 값을 다른 나이 데이터의 평균으로 변경
  mean_age = df['age'].mean()
  df['age'].fillna(mean_age, inplace=True)
  
  print(df['age'].head(10))
  
  '''
  0    22.0
  1    38.0
  2    26.0
  3    35.0
  4    35.0
  5     NaN
  6    54.0
  7     2.0
  8    27.0
  9    14.0
  Name: age, dtype: float64
  
  
  0    22.000000
  1    38.000000
  2    26.000000
  3    35.000000
  4    35.000000
  5    29.699118
  6    54.000000
  7     2.000000
  8    27.000000
  9    14.000000
  Name: age, dtype: float64
  '''
  ```

  



### 2. 중복 데이터 처리



#### 중복 데이터 확인



* `df.duplicated()`

  중복 데이터가 있는지 확인

  전에 나온 행들과 비교합니다.

  중복되는 행 : True

  처음 나오는 행: False

  ```python
  # 데이터프레임 전체 행 데이터 중에서 중복값 찾기
  # 처음 나오는 행은 False, 중복되는 행은 True !!!
  
  df_dup = df.duplicated()
  print(df_dup)
  
  '''
  0    False
  1     True
  2    False
  3    False
  4    False
  dtype: bool
  '''
  ```

  

#### 중복 데이터 제거



* `df.drop_duplicates(subset=None, keep='first', inplace=False)`

  중복되는 행을 제거

  ```python
  df2 = df.drop_duplicates()
  print(df2)
  
  '''
    c1  c2  c3
  0  a   1   1
  2  b   1   2
  3  a   2   2
  4  b   2   2
  '''
  
  df3 = df.drop_duplicates(subset=['c2', 'c3'])
  print(df3)
  
  '''
    c1  c2  c3
  0  a   1   1
  2  b   1   2
  3  a   2   2
  '''
  ```

  
