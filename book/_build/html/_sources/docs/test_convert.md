---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

(test_convert)=

# Pandas 한번에 제대로 배우기




---




```
import numpy as np
import pandas as pd
pd.__version__
```




    '1.5.3'



## Pandas 객체


### Series 객체


```
s = pd.Series([0, 0.25, 0.5, 0.75, 1.0])
s
```




    0    0.00
    1    0.25
    2    0.50
    3    0.75
    4    1.00
    dtype: float64




```
s.values
```




    array([0.  , 0.25, 0.5 , 0.75, 1.  ])




```
s.index
```




    RangeIndex(start=0, stop=5, step=1)




```
s[1:4]
```




    1    0.25
    2    0.50
    3    0.75
    dtype: float64




```
s = pd.Series([0, 0.25, 0.5, 0.75, 1.0],
              index=['a','b','c','d','e'])
s
```




    a    0.00
    b    0.25
    c    0.50
    d    0.75
    e    1.00
    dtype: float64




```
'b' in s
```




    True




```
s = pd.Series([0, 0.25, 0.5, 0.75, 1.0],
              index=['2','4','6','8','10'])
s
```




    2     0.00
    4     0.25
    6     0.50
    8     0.75
    10    1.00
    dtype: float64




```
s.unique()
```




    array([0.  , 0.25, 0.5 , 0.75, 1.  ])




```
s.value_counts()
```




    0.00    1
    0.25    1
    0.50    1
    0.75    1
    1.00    1
    dtype: int64




```
s.isin([0.25, 0.75])
```




    2     False
    4      True
    6     False
    8      True
    10    False
    dtype: bool




```
pop_tuple = {'서울특별시': 100000,
             '부산광역시': 10000,
             '인천광역시': 10020}
pop = pd.Series(pop_tuple)
pop
```




    서울특별시    100000
    부산광역시     10000
    인천광역시     10020
    dtype: int64




```

```




```

```


```

```


```

```


```

```


```

```


```

```

### DataFrame 객체


```
pd.DataFrame([{'A':2, 'B': 4, 'D':3},{'A':2, 'B': 4, 'C':3}])
```





  <div id="df-cdce33d2-1a22-41c1-8823-da3121b4c771">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>D</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2</td>
      <td>4</td>
      <td>3.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>4</td>
      <td>NaN</td>
      <td>3.0</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-cdce33d2-1a22-41c1-8823-da3121b4c771')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-cdce33d2-1a22-41c1-8823-da3121b4c771 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-cdce33d2-1a22-41c1-8823-da3121b4c771');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```
pd.DataFrame(np.random.rand(5,5),
             columns = ['A','B','C','D','E'],
             index=[1,2,3,4,5])
```





  <div id="df-d3f58f8d-c6bb-4d03-a79d-b9b897d32497">
    <div class="colab-df-container">
      <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
      <th>E</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>0.021232</td>
      <td>0.237302</td>
      <td>0.934066</td>
      <td>0.408532</td>
      <td>0.159284</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.838600</td>
      <td>0.666666</td>
      <td>0.375392</td>
      <td>0.576651</td>
      <td>0.148865</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0.097210</td>
      <td>0.600444</td>
      <td>0.258135</td>
      <td>0.887315</td>
      <td>0.189806</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0.981506</td>
      <td>0.592521</td>
      <td>0.225340</td>
      <td>0.081158</td>
      <td>0.536024</td>
    </tr>
    <tr>
      <th>5</th>
      <td>0.629624</td>
      <td>0.041720</td>
      <td>0.114870</td>
      <td>0.926746</td>
      <td>0.701059</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-d3f58f8d-c6bb-4d03-a79d-b9b897d32497')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-d3f58f8d-c6bb-4d03-a79d-b9b897d32497 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-d3f58f8d-c6bb-4d03-a79d-b9b897d32497');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>





```
male_tuple 
```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

### Index 객체



```

```


```

```


```

```


```

```


```

```


```

```

#### Index 연산


```

```



---



## 인덱싱(Indexing)


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

### Series 인덱싱


```

```


```

```


```

```


```

```


```

```


```

```


```

```

### DataFrame 인덱싱



```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

### 다중 인덱싱(Multi Indexing)

* 1차원의 Series와 2차원의 DataFrame 객체를 넘어 3차원, 4차원 이상의 고차원 데이터 처리
* 단일 인덱스 내에 여러 인덱스를 포함하는 다중 인덱싱

#### 다중 인덱스 Series


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

#### 다중 인덱스 생성


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

#### 인덱싱 및 슬라이싱


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

#### 다중 인덱스 재정렬


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

## 데이터 연산


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

### 연산자 범용 함수


#### add()


```

```


```

```


```

```


```

```


```

```

#### sub() / subtract()


```

```


```

```


```

```


```

```


```

```


```

```

#### mul() / multply()





```

```


```

```


```

```


```

```


```

```


```

```

#### truediv() /  div() / divide() / floordiv()


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

#### mod()


```

```


```

```


```

```


```

```

#### pow()


```

```


```

```


```

```


```

```


```

```


```

```

### 정렬(Sort)


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

### 순위(Ranking)



```

```


```

```


```

```


```

```

### 고성능 연산


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

## 데이터 결합

### Concat() / Append()


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

### 병합과 조인


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

## 데이터 집계와 그룹 연산

#### 집계 연산(Aggregation)



```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

### GroupBy 연산


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

### 피벗 테이블(Pivot Table)



```

```


```

```


```

```


```

```


```

```


```

```

### 범주형(Categorical) 데이터



```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

## 문자열 연산

#### 문자열 연산자


```

```


```

```


```

```


```

```

#### 기타 연산자



```

```


```

```


```

```


```

```

#### 정규표현식



```

```


```

```

## 시계열 처리


```

```


```

```


```

```


```

```

#### 시계열 데이터 구조



```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

### 시계열 기본


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

### 주기와 오프셋



```

```


```

```


```

```


```

```


```

```


```

```

### 시프트(Shift)


```

```


```

```


```

```


```

```


```

```


```

```

### 시간대 처리

* 국제표준시(Coordinated Universal Time, UTC)를 기준으로 떨어진 거리만큼 오프셋으로 시간대 처리
* 전 세계의 시간대 정보를 모아놓은 올슨 데이터베이스를 활용한 라이브러리인 `pytz` 사용


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

### 기간과 기간 연산


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

### 리샘플링(Resampling)

* 리샘플링(Resampling): 시계열의 빈도 변환
* 다운샘플링(Down sampling): 상위 빈도 데이터를 하위 빈도 데이터로 집계
* 업샘플링(Up sampling): 하위 빈도 데이터를 상위 빈도 데이터로 집계


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

### 무빙 윈도우(Moving Window)


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

## 데이터 읽기 및 저장


### 텍스트 파일 읽기/쓰기


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

### 이진 데이터 파일 읽기/쓰기


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

## 데이터 정제

### 누락값 처리

* 대부분의 실제 데이터들은 정제되지 않고 누락값들이 존재
* 서로 다른 데이터들은 다른 형태의 결측을 가짐
* 결측 데이터는 `null`, `NaN`, `NA`로 표기

#### None: 파이썬 누락 데이터


```

```


```

```

#### NaN: 누락된 수치 데이터


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

#### Null 값 처리



```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```


```

```

### 중복 제거


```

```


```

```


```

```

### 값 치환


```

```


```

```


```

```


```

```

## 참고문헌

* Pandas 사이트: https://pandas.pydata.org/
* Jake VanderPlas, "Python Data Science Handbook", O'Reilly
* Wes Mckinney, "Python for Data Analysis", O'Reilly
