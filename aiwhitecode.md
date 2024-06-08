___

## [0-1.기본 명령어]

> ## Jupyter Notebook 명령어
> Shift + Enter : 셀실행 후, 아래셀 선택  
> Alt + Enter : 셀실행 후, 아래 빈쉘 생성  
> Ctrl + Enter : 셀실행  
> A : 바깥에서 위쪽 빈쉘 생성  
> B : 바깥에서 아래 빈쉘 생성  
> dd : 바깥에서 해당쉘 삭제

___

## [0-2.도구 불러오기]

> ## pandas 불러오고, pd로 정의
> ```python
> import pandas as pd
> ```
> ## numpy 불러오고, np로 정의
> ```python
> import numpy as np
> ```
> ## seaborn 설치 및 불러오고, sns로 정의
>(!: 리눅스 프롬프트 명령어)
> ```python
> !pip install seaborn
> import seaborn as sns
> ```
> ## matplot 불러오고, plt로 정의
>(%: 주피터랩 명령어)
> ```python
> %matplotlib inline
> import matplotlib.pylot as plt
> ```
> ## 텐서플로 불러오고, tf로 정의
> ```python
> import tensorflow as tf
> ```
> ## 텐서플로 케라스모델 및 기능 불러오기
> (시퀀스(히든레이어개수)/덴스(노드개수)/액티베이션/과적합방지기능 불러오기)
> ```python
> from tensorflow.keras.models import Sequential
> from tensorflow.keras.layers import Dense, Activation, Dropout
> ```
> ## \[모델\] sklearn에서, 선형회귀모델(LinearRegression) 불러오기
> ```
> from sklearn.family import model
> from sklearn.linear_model import LinearRegression
> ```
> ## \[모델\] sklearn에서, 분류회귀모델(Logistic Regression) 불러오기
> (설명: 분류모델 주로 활용)
> ```
> from sklearn.linear_model import LogisticRegression
> from sklearn.model_selection import train_test_split
> from sklearn.metrics import classification_report 
> ```
> ## \[모델\] sklearn에서, 랜덤포레스트 불러오기
> (설명: 의사결정나무 2개에서, 여러개를 더해 예측율을 높임)
> ```
> from sklearn.tree import DecisionTreeClassifier
> ```
> ## \[모델\] sklearn에서, 의사결정나무 불러오기
> (설명: 분류/회귀가능한 다재다능, 다소복잡한 데이터셋도 학습가능)
> ```
> from sklearn.tree import DecisionTreeClassifier
> ```
> ## \[모델\] AdaBoost
> ## \[모델\] GBM (Gradient Boost)
> ## \[모델\] XGBoost
> (설명: GBM의 느림, 과적합 방지를 위해 Regulation만 추가, 리소스를 적게 먹으며 조기종료 제공)
> ## \[모델\] SVM (Support Vector Machine)
> ## \[모델\] Auto Encoder
> ## \[모델\] CNN
> ## \[모델\] RNN
> ## \[모델\] LSTM
> ## \[모델\] Transformer
> ## \[모델\] SES (Simple Exponential Smoothing)
> ## \[모델\] YOLO
> ## \[모델\] VGG

___

## \[1-1.빅데이터 수집\]
> ## “00000.csv” 데이터 로드
> (cp949는 MS office에서 인코딩할때 쓰임)
> ```
> df = pd.read_csv ("./00000.csv", encoding = "cp949")
> ```
> ## 커스텀 프레임웍에서 “00000.csv” 데이터 로드 2
> (custom\_framework.config.data\_dir 폴더에서 불러옴)
> ```
> df = pd.read_csv (custom_framework.config.data_dir + "/00000.csv")
> ```
> ## 파일위치 환경변수
> data 경로: custom\_framework.config.data\_dir  
> workspace 경로: custom\_framework.config.workspace\_dir  
> model 경로: custom\_framework.config.model\_dir  
> log 경로: custom\_framework.config.workspace\_logs
> ## “00000\_final.csv” 데이터 저장 1
> ```
> df.to_csv ("00000_final.csv", index = false)
> ```
> ## “00000\_final.xlsx” 엑셀로 저장 2
> ```
> df.to_excel ("00000.xlsx")
> ```

___

## \[1-2.빅데이터 분석\]
Column Names = 열  
index = 행  
value = 값(행들의 데이터)
> ## df데이터 / 처음 위(head)아래(tail) 10개행을 보여주기
> ```
> df.head( )
> df.head(10)
> df.tail(10)
> ```
> ## df데이터 / 형태(column/row수) 확인
> ```
> df.shape
> ```
> ## df데이터 / 컬럼내역 출력 (열,세로)
> ```
> df.columns
> ```
> ## df데이터 / 로우내역 출력 (행,가로)
> ```
> df.values
> ```
> ## df데이터 / 자료구조 파악
> ```
> df.info( )
> ```
> ## df데이터 / 타입 확인
> ```
> df.dtypes 
> ```
> ## df데이터 / 통계정보
> mean(평균), std(분산), min/max(최소/최대값)  
> ※ df.describe( ).transpose( )
> ```
> df.describe( )
> ```
> ## df데이터 / 상관관계 분석
> ```
> df.corr( )
> ```
> ## 데이터 뽑아오기
> ```
> x[0]  ## x의 0번째 데이터 뽑아오기
> x[-1]  ## x의 뒤에서 1번째 데이터 뽑아오기
> x[0:4]  ## x의 0~4번째까지 데이터 뽑아오기
> x[:]  ## x의 전체 데이터 뽑아오기
> ```
> ## df데이터 / “00000”컬럼의 데이터 확인
> ```
> df["00000"]
> ```
> ## df데이터 / “00000”컬럼의 값분포 확인
> ```
> df["00000"].value_counts()
> ```
> ## df데이터 / “00000”칼럼의 값비율 확인
> ```
> df["00000"].value_counts(normalize=True)
> ```

___

## \[1-3.빅데이터 시각화\]

> ## \[Matplotlib\] 시각화 (스캐터,바챠트)
> 영역 지정 : plt.figure()  
> 차트/값 지정 : plt.plot()  
> 시각화 출력 : plt.show()  
>> ### df데이터 / “00000”칼럼, 바차트 시각화 1 (이산)
>> ```
>> df["00000"].value_counts( ).plot(kind="bar")
>> plt.show( )
>> ```
>> ### df데이터 / “00000”칼럼, 바차트 시각화 2
>> ```
>> df.corr( )["00000"][:-1].sort_values( ).plot(kind="bar")
>> sns.pairplot(df)
>> ```
>> ### df데이터 / “A.B”칼럼, 히스토그램 시각화 (연속)
>> ```
>> df["A.B"].plot(kind="hist")
>> plt.show( )
>> ```
>> ```
>> df["00000"].plot(kind="hist")
>> ```
>> ### 바 플롯
>> ```
>> plt.bar(x, height)
>> ```
>> ### 히스토그램
>> ```
>> plt.hist(x)
>> ```
>> ### 산점도
>> ```
>> plt.scatter(x, y)
>> ```
>> ### 색깔별 산점도 시각화
>> ```
>> groups = df.groupby('variety')
>> groups
>> for name,group in groups :
>>  plt.scatter(x = 'A', y = 'B', data = group, label = name)
>> plt.legend()  ## 범례 추가
>> plt.show()
>> ```
>> ### 선 그래프
>> ```
>> plt.plot(data)
>> ```
> ## \[Seaborn\] 시각화 (히트맵, 통계)
>> ### 카운트 플롯
>> ```
>> sns.countplot(x="A", data=df)
>> ```
>> ### 박스 플롯
>> ```
>> sns.boxplot(x="A", y="B", data=df)
>> ```
>> ### 조인트 플롯
>> ```
>> sns.jointplot(x="A", y="B", data=df, kind="hex")
>> ```
>> ### 상관관계 히트맵
>> ```
>> sns.heatmap(df.corr( ), annot=True)
>> ```
>> ```
>> corr = jiro_df.corr()  ## corr함수로 상관계수 구하기
>> sns.heatmap(corr,annot=True)  ## annotation 포함
>> ```

___

## \[1-4.빅데이터 전처리\]
최고빈번값(Most frequent), 중앙값(Median), 평균값(Mean), 상수값(Constant)

> ## 입력데이터에서 제외
> ※ axis=0(행), axis=1(열)
> ```
> drop( )
> ```
> ```
> df = df.drop('A', axis=1)
> ```
> ## 누락데이터 처리
> ※ axis=0(행), axis=1(열)
> ```
> replace( )
> ```
> ## 결측치
>> ## df데이터 / 칼럼마다 결측치 여부 확인
>> ```
>> df.isnull().sum()
>> ```
>> ## 결측치(Null데이터) 처리
>> ```
>> dropna( ), fillna( ) 
>> ```
>> ```
>> df['float_A'] = df['float_A'].fillna(0)  ##float_A열 결측치 0으로 채우기
>> ```
>> ## 결측치 처리
>> missing(결측값수)  
>> “_“를 numpy의 null값(결측치)으로 변경
>> ```
>> df = df.replace("_", np.NaN)
>> ```
>> ## “Class” 열의 결측치값 제외시키기
>> ```
>> df.dropna(subset=["class"])
>> ```
>> ## Listwise 결측치 행 제외시키기
>> (행의 1개값이라도 NaN이면 제외)
>> ```
>> df.dropna()
>> ```
>> ## Pairwise 결측치 행 제외시키기
>> (행의 모든값이 NaN일때 제외)
>> ```
>> df.dropna(how="all")
>> ```
>> ## Most frequent(최빈)값 대체하여 채우기
>> (범주형데이터 주로사용)  
>> df데이터 / 모두
>> ```
>> df.fillna(df.mode().iloc[0])
>> ```
>> df데이터 / “A”칼럼 결측치를 해당칼럼 최빈값으로 채우기
>> ```
>> df["A"].fillna(df["A"].mode()[0])
>> ```
>> ## mean(평균), median(중간)값 대체하여 채우기
>> (범주형데이터 주로사용)
>> ```
>> df.fillna(df.mean()["C1":"C2"])
>> ```
>> ## 앞값(ffill), 뒷값(backfill) 대체하여 채우기
>> ```
>> df = df.fillna(method="ffill")
>> ```
>> ## 주변값과 상관관계로 선형 채우기
>> (선형관계형 데이터에서 주로사용)
>> ```
>> df = df.interpolate()
>> ```
> ## 아웃라이어
>> ## 아웃라이어 제외
>> Class열의 H값 제외후 변경
>> ```
>> df = df [(df["class"]! = "H")]
>> ```
>> ## 아웃라이어 변경
>> Class열의 H값을 F값으로 변경
>> ```
>> df["class"] = df["class"].replace("H", "F")
>> ```
>> 제거기준 = (Q3 + IQR \* 1.5 보다 큰 값) & (Q1 - IQR \* 1.5 보다 작은 값)
>> 가.Q1, Q3, IQR 정의 IQR = Q3(3사분위수)-Q1(1사분위수)
>> ```
>> Q1 = df[["Dividend","PBR"]].quantile(q=0.25)
>> Q3 = df[["Dividend","PBR"]].quantile(q=0.75)
>> IQR = Q3-Q1
>> ```
>> 나.변경
>> ```
>> IQR_df = df[(df["Dividend"] <= Q3["Dividend"]+1.5*IQR["Dividend"]) & (df["Dividend"] >= Q1["Dividend"]-1.5*IQR["Dividend"])]
>> IQR_df = IQR_df[(IQR_df["PBR"] <= Q3["PBR"]+1.5*IQR["PBR"]) & (IQR_df["PBR"] >= Q1["PBR"]-1.5*IQR["PBR"])]
>> IQR_df = IQR_df[["Dividend","PBR"]]
>> ```
>> 다.확인(박스플롯)
>> ```
>> IQR_df.boxplot()
>> IQR_df.hist(bins=20, figsize=(10,5))
>> ```
> ## Feature Engineering
>> ## 비닝(Binning)
>> 연속형 변수를 범주형 변수로 만드는 방법
>> 비닝 / cut : (구간값으로 나누기)
>> ```
>> q1 = df["avg_bill"].quantile(0.25)
>> q3 = df["avg_bill"].quantile(0.75)
>> 
>> df["bill_rating"] = pd.cut(
>>                 df["avg_bill"],
>>                 bins = [0, q1, q3, df["avg_bill"].max()],
>>                 labels = ["low", "mid", "high"])
>> print (df["bill_rating"].value_counts()]
>> ```
>> 비닝 / qcut : (구간개수로 나누기)
>> ```
>> df["bill_rating"] = pd.qcut(
>>                 df["avg_bill"],
>>                 3,
>>                 labels=["low", "mid", ;high"])
>> print (df["bill_rating"].value_counts()]
>> ```

## 스케일링(Scaling)[](https://lovespacewhite.github.io/#%EC%8A%A4%EC%BC%80%EC%9D%BC%EB%A7%81scaling)

데이터 단위크기를 맞춤으로서 표준화/정규화

Standard Scaling :  
평균을 0, 표준편차를 1로 맞추기 (데이터 이상치가 심할경우 사용)

```
<span>df_num</span> <span>=</span> <span>df</span><span>[[</span><span>"avg_bill"</span><span>,</span> <span>"A_bill"</span><span>,</span> <span>"B_bill"</span><span>]]</span>
<span>Standardization_df</span> <span>=</span> <span>(</span><span>df_num</span> <span>-</span> <span>df_num</span><span>.</span><span>mean</span><span>())</span> <span>/</span> <span>df_num</span><span>.</span><span>std</span><span>()</span>
```

```
<span>from</span> <span>sklearn.preprocessing</span> <span>import</span> <span>StandardScaler</span>
<span>scaler</span><span>=</span><span>StandardScaler</span><span>()</span>

<span>X_train2</span> <span>=</span> <span>scaler</span><span>.</span><span>fit_transform</span><span>(</span><span>X_train1</span><span>)</span>  <span>## 정규분포화
</span><span>X_train2</span> <span>=</span> <span>scaler</span><span>.</span><span>transform</span><span>(</span><span>X_train1</span><span>)</span>  <span>## 표준화
</span>
```

Min-Max Scaling : 모든 데이터를 0~1사이로 맞추기

```
<span>from</span> <span>sklearn.preprocessing</span> <span>import</span> <span>MinMaxScaler</span>
<span>scaler</span><span>=</span><span>MinMaxScaler</span><span>()</span>
<span>nomalization_df</span> <span>=</span> <span>df_num</span><span>.</span><span>copy</span><span>()</span>
<span>nomalization_df</span><span>[:]</span> <span>=</span> <span>scaler</span><span>.</span><span>fit_transform</span><span>(</span><span>normalization_df</span><span>[:])</span>
```

\-

## 라벨인코딩

```
<span>from</span> <span>sklearn.preprocessing</span> <span>import</span> <span>LabelEncoder</span>
<span>lb</span> <span>=</span> <span>LabelEncoder</span><span>()</span>
<span>df</span><span>[</span><span>'A'</span><span>]</span> <span>=</span> <span>lb</span><span>.</span><span>fit_transform</span><span>(</span><span>df</span><span>[</span><span>'A'</span><span>]</span>
<span>df</span>
```

\-

## 원핫인코딩

## 카테고리형 데이터를 원핫인코딩으로 컬럼 작성[](https://lovespacewhite.github.io/#%EC%B9%B4%ED%85%8C%EA%B3%A0%EB%A6%AC%ED%98%95-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EC%9B%90%ED%95%AB%EC%9D%B8%EC%BD%94%EB%94%A9%EC%9C%BC%EB%A1%9C-%EC%BB%AC%EB%9F%BC-%EC%9E%91%EC%84%B1)

```
<span>cols</span> <span>=</span> <span>[</span><span>"Gender"</span><span>,</span> <span>"Partner"</span><span>,</span> <span>"Dependents"</span><span>,</span> <span>"PhoneService"</span><span>,</span>
 <span>"MultipleLines"</span><span>,</span> <span>"InternetService"</span><span>,</span> <span>"OnlineSecurity"</span><span>,</span>
 <span>"OnlineBackup"</span><span>,</span> <span>"DeviceProtection"</span><span>,</span> <span>"TechSupport"</span><span>,</span> <span>"StreamingTV"</span><span>,</span>
 <span>"StreamingMovies"</span><span>,</span> <span>"Contract"</span><span>,</span> <span>"PaperlessBilling"</span><span>,</span> <span>"PaymentMethod"</span><span>]</span>

<span>dummies</span> <span>=</span> <span>pd</span><span>.</span><span>get_dummies</span><span>(</span><span>df</span><span>[</span><span>cols</span><span>],</span> <span>drop_first</span><span>=</span><span>True</span><span>)</span>
<span>df</span> <span>=</span> <span>df</span><span>.</span><span>drop</span><span>(</span><span>cols</span><span>,</span> <span>axis</span><span>=</span><span>1</span><span>)</span>
<span>df</span> <span>=</span> <span>pd</span><span>.</span><span>concat</span><span>([</span><span>df</span><span>,</span> <span>dummies</span><span>],</span> <span>axis</span><span>=</span><span>1</span><span>)</span>
```

## 카테고리형 데이터를 판다스로 쉽게 원핫인코딩[](https://lovespacewhite.github.io/#%EC%B9%B4%ED%85%8C%EA%B3%A0%EB%A6%AC%ED%98%95-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%ED%8C%90%EB%8B%A4%EC%8A%A4%EB%A1%9C-%EC%89%BD%EA%B2%8C-%EC%9B%90%ED%95%AB%EC%9D%B8%EC%BD%94%EB%94%A9)

```
<span>data</span> <span>=</span> <span>df</span><span>[[</span><span>"AA"</span><span>,</span><span>"BB"</span><span>]]</span>
<span>one_hot_df</span> <span>=</span> <span>pd</span><span>.</span><span>get_dummies</span><span>(</span><span>data</span><span>,</span> <span>columns</span><span>=</span><span>[</span><span>"class"</span><span>])</span>
<span>one_hot_df</span>
```

\-

## OrdinalEncoding

Categorical feature(범주형 특성)에 대한 순서형 코딩  
각 범주들을 특성으로 변경하지 않고, 그 안에서 1,2,3 등의 숫자로 변경  
범주가 너무 많아 one hot encoding을 하기 애매한 상황에서 이용

```
<span>from</span> <span>category_encoders</span> <span>import</span> <span>OrdinalEncoder</span>
<span>enc1</span> <span>=</span> <span>OrdinalEncoder</span><span>(</span><span>cols</span> <span>=</span> <span>"color"</span><span>)</span>
<span>df2</span> <span>=</span> <span>enc1</span><span>.</span><span>fit_transform</span><span>(</span><span>df2</span><span>)</span>
<span>df2</span>
```

___

## 기타 주요작업

## 토탈차지 공백을 0으로 변경후, 소수점 숫자형(float타입)으로 변경[](https://lovespacewhite.github.io/#%ED%86%A0%ED%83%88%EC%B0%A8%EC%A7%80-%EA%B3%B5%EB%B0%B1%EC%9D%84-0%EC%9C%BC%EB%A1%9C-%EB%B3%80%EA%B2%BD%ED%9B%84-%EC%86%8C%EC%88%98%EC%A0%90-%EC%88%AB%EC%9E%90%ED%98%95float%ED%83%80%EC%9E%85%EC%9C%BC%EB%A1%9C-%EB%B3%80%EA%B2%BD)

```
<span>df</span><span>[</span><span>"TotalCharge"</span><span>].</span><span>replace</span><span>([</span><span>" "</span><span>],</span> <span>[</span><span>"0"</span><span>],</span> <span>inplace</span><span>=</span><span>True</span><span>)</span>
<span>df</span><span>[</span><span>"TotalCharge"</span><span>]</span> <span>=</span> <span>df</span><span>[</span><span>"TotalCharge"</span><span>].</span><span>astype</span><span>(</span><span>float</span><span>)</span>
```

## 해지여부 Yes/No를 1,0의 정수형으로 변경[](https://lovespacewhite.github.io/#%ED%95%B4%EC%A7%80%EC%97%AC%EB%B6%80-yesno%EB%A5%BC-10%EC%9D%98-%EC%A0%95%EC%88%98%ED%98%95%EC%9C%BC%EB%A1%9C-%EB%B3%80%EA%B2%BD)

```
<span>df</span><span>[</span><span>"Churn"</span><span>].</span><span>replace</span><span>([</span><span>"Yes"</span><span>,</span> <span>"No"</span><span>],</span> <span>[</span><span>1</span><span>,</span> <span>0</span><span>],</span> <span>inplace</span><span>=</span><span>True</span><span>)</span>
```

## 새로운 뉴피처 추가[](https://lovespacewhite.github.io/#%EC%83%88%EB%A1%9C%EC%9A%B4-%EB%89%B4%ED%94%BC%EC%B2%98-%EC%B6%94%EA%B0%80)

```
<span>df</span><span>[</span><span>"new_feature"</span><span>]</span> <span>=</span> <span>df</span><span>[</span><span>"f_1"</span><span>]</span><span>/</span><span>df</span><span>[</span><span>"f_2"</span><span>]</span>
```

## distinct 피처 제외 (값종류수)[](https://lovespacewhite.github.io/#distinct-%ED%94%BC%EC%B2%98-%EC%A0%9C%EC%99%B8-%EA%B0%92%EC%A2%85%EB%A5%98%EC%88%98)

distinct=1인 경우, 모든컬럼이 동일하므로 피처에서 제외

## 편향값[](https://lovespacewhite.github.io/#%ED%8E%B8%ED%96%A5%EA%B0%92)

## 순서(인덱스)는 의미의 유무에 따라 제외[](https://lovespacewhite.github.io/#%EC%88%9C%EC%84%9C%EC%9D%B8%EB%8D%B1%EC%8A%A4%EB%8A%94-%EC%9D%98%EB%AF%B8%EC%9D%98-%EC%9C%A0%EB%AC%B4%EC%97%90-%EB%94%B0%EB%9D%BC-%EC%A0%9C%EC%99%B8)

___

## \[1-5.세트 구성\]

## 트레이닝/테스트 세트 나누기[](https://lovespacewhite.github.io/#%ED%8A%B8%EB%A0%88%EC%9D%B4%EB%8B%9D%ED%85%8C%EC%8A%A4%ED%8A%B8-%EC%84%B8%ED%8A%B8-%EB%82%98%EB%88%84%EA%B8%B0)

```
<span>from</span> <span>sklearn.model_selection</span> <span>import</span> <span>train_test_split</span> 
```

## X,y데이터 설정하기[](https://lovespacewhite.github.io/#xy%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0)

‘Answer’ 칼럼이 y값/타겟/레이블

```
<span>X</span> <span>=</span> <span>df</span><span>.</span><span>drop</span><span>(</span><span>'Answer'</span><span>,</span><span>axis</span><span>=</span><span>1</span><span>).</span><span>values</span>
<span>y</span> <span>=</span> <span>df</span><span>[</span><span>'Answer'</span><span>].</span><span>values</span>
```

## X,y데이터 불러오기[](https://lovespacewhite.github.io/#xy%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B6%88%EB%9F%AC%EC%98%A4%EA%B8%B0)

reshape(-1,1) 2차원배열 디자인포맷(reshape) 확장(-1은 알아서 넣으라는 뜻)

```
<span>X</span> <span>=</span> <span>np</span><span>.</span><span>array</span><span>([</span><span>1</span><span>,</span> <span>2</span><span>,</span> <span>3</span><span>,</span> <span>4</span><span>,</span> <span>5</span><span>,</span> <span>6</span><span>,</span> <span>7</span><span>,</span> <span>8</span><span>,</span> <span>9</span><span>,</span> <span>10</span><span>]).</span><span>resharpe</span><span>(</span><span>-</span><span>1</span><span>,</span><span>1</span><span>)</span>
<span>y</span> <span>=</span> <span>np</span><span>.</span><span>array</span><span>([</span><span>13</span><span>,</span> <span>25</span><span>,</span> <span>34</span><span>,</span> <span>47</span><span>,</span> <span>59</span><span>,</span> <span>62</span><span>,</span> <span>79</span><span>,</span> <span>88</span><span>,</span> <span>90</span><span>,</span> <span>100</span><span>])</span>
```

## 테스트세트를 30%로 분류하고, 50번 랜덤하게 섞기[](https://lovespacewhite.github.io/#%ED%85%8C%EC%8A%A4%ED%8A%B8%EC%84%B8%ED%8A%B8%EB%A5%BC-30%EB%A1%9C-%EB%B6%84%EB%A5%98%ED%95%98%EA%B3%A0-50%EB%B2%88-%EB%9E%9C%EB%8D%A4%ED%95%98%EA%B2%8C-%EC%84%9E%EA%B8%B0)

(y값이 골고루 분할되도록 stratify하게 분할)

```
<span>X_train</span><span>,</span> <span>X_test</span><span>,</span> <span>y_test</span> <span>=</span>
  <span>train_test_split</span>
  <span>(</span><span>X</span><span>,</span> <span>y</span><span>,</span> <span>test_size</span><span>=</span><span>0.30</span><span>,</span> <span>random_state</span><span>=</span><span>50</span><span>,</span> <span>stratify</span> <span>=</span> <span>y</span><span>)</span>
```

```
<span>(</span><span>데이터</span> <span>정규화</span><span>/</span><span>스케일링</span><span>)</span>  
<span>from</span> <span>sklearn.preprocessing</span> <span>import</span> <span>MinMaxScaler</span>
<span>help</span><span>(</span><span>MinMaxScaler</span><span>)</span>
<span>scaler</span> <span>=</span> <span>MinMaxScaler</span><span>(</span> <span>)</span>
<span>scaler</span><span>.</span><span>fit</span><span>(</span><span>X_train</span><span>)</span>
<span>X_train</span> <span>=</span> <span>scaler</span><span>.</span><span>transform</span><span>(</span><span>X_train</span><span>)</span>
<span>X_test</span> <span>=</span> <span>scaler</span><span>.</span><span>transform</span><span>(</span><span>X_test</span><span>)</span>
```

___

## \[2.학습모델\] ~ \[3.최적화\]

## LinearRegression 모델 (선형회귀)[](https://lovespacewhite.github.io/#linearregression-%EB%AA%A8%EB%8D%B8-%EC%84%A0%ED%98%95%ED%9A%8C%EA%B7%80)

가. 모델 선정

```
<span>model</span> <span>=</span> <span>LinearRegression</span><span>(</span> <span>)</span>
```

나. 테스트 핏

```
<span>model</span><span>.</span><span>fit</span><span>(</span><span>X_train</span><span>,</span> <span>y_train</span><span>)</span>  
```

다. 예측

```
<span>linearR_pred</span> <span>=</span> <span>model</span><span>.</span><span>predict</span><span>(</span><span>X_test</span><span>)</span>
```

라. 확인

회귀예측 주요 성과지표

```
<span>import</span> <span>numpy</span> <span>as</span> <span>np</span>
<span>np</span><span>.</span><span>mean</span><span>((</span><span>y_pred</span> <span>-</span> <span>y_test</span><span>)</span> <span>**</span> <span>2</span><span>)</span> <span>**</span> <span>0.5</span>
```

___

## Logistic Regression 모델 (분류회귀)[](https://lovespacewhite.github.io/#logistic-regression-%EB%AA%A8%EB%8D%B8-%EB%B6%84%EB%A5%98%ED%9A%8C%EA%B7%80)

가. 라이브러리 불러오기

```
<span>from</span> <span>sklearn.linear_model</span> <span>import</span> <span>LogisticRegression</span>
<span>from</span> <span>sklearn.model_selection</span> <span>import</span> <span>train_test_split</span>
<span>from</span> <span>sklearn.metrics</span> <span>import</span> <span>classification_report</span>
```

나. 데이터 불러오기

```
<span>train</span> <span>=</span> <span>pd</span><span>.</span><span>read_csv</span><span>(</span><span>custom_framework</span><span>.</span><span>config</span><span>.</span><span>data_dir</span> <span>+</span> <span>"/train.csv"</span><span>)</span>
```

다. 세트 나누기

```
<span>X_train</span><span>,</span> <span>X_test</span><span>,</span> <span>y_train</span><span>,</span> <span>y_test</span><span>,</span> <span>=</span> <span>train_test_split</span><span>(</span>
                 <span>train</span><span>.</span><span>drop</span><span>(</span><span>"OOO"</span><span>,</span> <span>axis</span><span>=</span><span>1</span><span>),</span>
                 <span>train</span><span>[</span><span>"OOO"</span><span>],</span> <span>test_size</span><span>=</span><span>0.30</span><span>,</span> <span>random_state</span><span>=</span><span>42</span><span>)</span>
```

라. 모델링

```
<span>model</span> <span>=</span> <span>LogisticRegression</span><span>(</span> <span>)</span>   
<span>model</span><span>.</span><span>fit</span><span>(</span><span>x_train</span><span>,</span> <span>y_train</span><span>)</span>
<span>LogisticR_pred</span> <span>=</span> <span>model</span><span>.</span><span>predict</span><span>(</span><span>x_test</span><span>)</span>
<span>print</span><span>(</span><span>classification_report</span><span>(</span><span>y_test</span><span>,</span> <span>LogisticR_pred</span><span>)</span>
```

___

## 의사결정나무(Decision Tree) (선형회귀)[](https://lovespacewhite.github.io/#%EC%9D%98%EC%82%AC%EA%B2%B0%EC%A0%95%EB%82%98%EB%AC%B4decision-tree-%EC%84%A0%ED%98%95%ED%9A%8C%EA%B7%80)

분류/회귀가능한 다재다능, 다소복잡한 데이터셋도 학습가능

가. 의사결정나무 라이브러리 불러오기

```
<span>from</span> <span>sklearn.tree</span> <span>import</span> <span>DecisionTreeClassifier</span> 
```

나. 데이터셋(df) 불러오기

```
<span>model</span> <span>=</span> <span>DecisionTreeClassifier</span><span>(</span><span>max_depth</span><span>=</span><span>10</span><span>,</span><span>random_state</span><span>=</span><span>42</span><span>)</span>
<span>model</span><span>.</span><span>fit</span><span>(</span><span>X_train</span><span>,</span><span>y_train</span><span>)</span>
<span>dt_pred</span> <span>=</span> <span>model</span><span>.</span><span>predict</span><span>(</span><span>X_test</span><span>)</span>
<span>accuracy_eval</span><span>(</span><span>'DecisionTree'</span><span>,</span><span>dt_pred</span><span>,</span><span>y_test</span><span>)</span> 
```

___

## Ensemble 기법[](https://lovespacewhite.github.io/#ensemble-%EA%B8%B0%EB%B2%95)

1) Bagging  
2) Boosting : 이전학습 잘못예측한 데이터에 가중치부여해 오차보완  
3) Stacking : 여러개 모델이 예측한 결과데이터 기반, final\_estimator모델로 종합 예측수행 4) Weighted Blending : 각모델 예측값에 대해 weight 곱하여 최종 아웃풋계산

\-

## XGBoost[](https://lovespacewhite.github.io/#xgboost)

(!는 리눅스 명령어)

```
<span>!</span><span>pip</span> <span>install</span> <span>xgboost</span>

<span>from</span> <span>xgboost</span> <span>import</span> <span>XGBClassfier</span>
<span>model</span> <span>=</span> <span>XGBClassifier</span><span>(</span><span>n_estimators</span><span>=</span><span>50</span><span>)</span>
<span>model</span><span>.</span><span>fit</span><span>(</span><span>X_train</span><span>,</span><span>y_train</span><span>)</span>
<span>xgb_pred</span> <span>=</span> <span>model</span><span>.</span><span>predict</span><span>(</span><span>X_test</span><span>)</span>
<span>accuracy_eval</span><span>(</span><span>'XGBoost'</span><span>,</span><span>xgb_pred</span><span>,</span> <span>y_test</span><span>)</span>
```

## LightGBM[](https://lovespacewhite.github.io/#lightgbm)

```
<span>!</span><span>pip</span> <span>install</span> <span>lightGBM</span>

<span>from</span> <span>xgboost</span> <span>import</span> <span>GBMClassfier</span>
<span>model</span> <span>=</span> <span>LGBMClassifier</span><span>(</span><span>n_estimators</span><span>=</span><span>3</span><span>,</span> <span>random_state</span><span>=</span><span>42</span><span>)</span>
<span>model</span><span>.</span><span>fit</span><span>(</span><span>X_train</span><span>,</span><span>y_train</span><span>)</span>
<span>lgbm_pred</span> <span>=</span> <span>model</span><span>.</span><span>predict</span><span>(</span><span>X_test</span><span>)</span>
<span>accuracy_eval</span><span>(</span><span>'lgbm'</span><span>,</span><span>lgbm_pred</span><span>,</span><span>y_test</span><span>)</span>
```

\-

## KNN (K-Nearest Neighbor)[](https://lovespacewhite.github.io/#knn-k-nearest-neighbor)

```
<span>from</span> <span>sklearn.neighbors</span> <span>import</span> <span>KNeighborsClassifier</span>
<span>model</span> <span>=</span> <span>KneighborsClassifier</span><span>(</span><span>n_neighbors</span><span>=</span><span>5</span><span>)</span>
<span>model</span><span>.</span><span>fit</span><span>(</span><span>X_train</span><span>,</span><span>y_train</span><span>)</span>
<span>knn_pred</span> <span>=</span> <span>model</span><span>.</span><span>predict</span><span>(</span><span>X_test</span><span>)</span>
<span>accuracy_eval</span><span>(</span><span>'K-Nearest Neighbor'</span><span>,</span><span>knn_pred</span><span>,</span><span>y_test</span><span>)</span>
```

\-

## Random Forest[](https://lovespacewhite.github.io/#random-forest)

선형회귀모델 중 하나  
의사결정나무 2개에서, 여러개를 더해 예측율을 높임

가. 랜덤포레스트 불러오기

```
<span>from</span> <span>sklearn.ensemble</span> <span>import</span> <span>RandomForestRegressor</span>
```

나. model 랜덤포레스트 선정

```
<span>model</span> <span>=</span> <span>RandomForestRegressor</span>
                 <span>(</span><span>n_estimators</span><span>=</span><span>50</span><span>,</span> <span>##학습시 생성할 트리갯수
</span>                 <span>max_depth</span><span>=</span><span>20</span><span>,</span> <span>##트리의 최대 깊이
</span>                 <span>random_state</span><span>=</span><span>42</span><span>,</span> <span>##난수 seed 설정
</span>                 <span>...,</span>
                 <span>criterion</span><span>=</span><span>"gini"</span><span>,</span> <span>##분할 품질을 측정하는 기능(디폴트:gini)
</span>                 <span>min_samples_split</span><span>=</span><span>2</span><span>,</span> <span>##내부노드를 분할하는데 필요한 최소샘플수
</span>                 <span>min_samples_leaf</span><span>=</span><span>1</span><span>,</span> <span>##리프노드에 있어야할 최소샘플수
</span>                 <span>min_weight_fraction_leaf</span><span>=</span><span>0.0</span><span>,</span> <span>##가중치가 부여된 min_samples_leaf에서의 샘플수 비율
</span>                 <span>max_feature</span><span>=</span><span>"auto"</span><span>)</span> <span>##각노드에서 분할에 사용할 특징의 최대수
</span>
```

다. 테스트 핏

```
<span>model</span><span>.</span><span>fit</span><span>(</span><span>x_train</span><span>,</span> <span>y_train</span><span>)</span>
```

라. 스코어

```
<span>model</span><span>.</span><span>score</span><span>(</span><span>x_test</span><span>,</span> <span>y_test</span><span>)</span>
```

마. 예측

```
<span>rf_pred</span> <span>=</span> <span>model</span><span>.</span><span>predict</span><span>(</span><span>x_test</span><span>)</span>  
```

바. RMSE값 구하기

```
<span>np</span><span>.</span><span>mean</span><span>((</span><span>y_pred</span> <span>-</span> <span>y_test</span><span>)</span> <span>**</span> <span>2</span><span>)</span> <span>**</span> <span>0.5</span>  
```

___

## 딥러닝 모델[](https://lovespacewhite.github.io/#%EB%94%A5%EB%9F%AC%EB%8B%9D-%EB%AA%A8%EB%8D%B8)

가. 케라스 초기화

```
<span>keras</span><span>.</span><span>backend</span><span>.</span><span>clear_session</span><span>(</span> <span>)</span>
```

나. 모델 작성 30개의 features, 보통 연산효율을 위해 relu활용  
Batchnormalization 활용  
과적합 방지  
input layer(30features), 2 hidden layer, output layer(이진분류)

```
<span>model</span> <span>=</span> <span>Sequential</span><span>(</span> <span>)</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>Dense</span><span>(</span><span>64</span><span>,</span> <span>activation</span><span>=</span><span>"relu"</span><span>,</span> <span>input_shape</span><span>=</span><span>(</span><span>30</span><span>,)))</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>BatchNormalization</span><span>(</span> <span>))</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>dropout</span><span>(</span><span>0.5</span><span>))</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>Dense</span><span>(</span><span>64</span><span>,</span> <span>activation</span><span>=</span><span>"relu"</span><span>))</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>BatchNormalization</span><span>(</span> <span>))</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>dropout</span><span>(</span><span>0.5</span><span>))</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>Dense</span><span>(</span><span>32</span><span>,</span> <span>activation</span><span>=</span><span>"relu"</span><span>))</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>dropout</span><span>(</span><span>0.5</span><span>))</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>Dense</span><span>(</span><span>1</span><span>,</span> <span>activation</span><span>=</span><span>"sigmoid"</span><span>))</span>
<span>#### 또는 output layer ()
</span>
```

(※ 아웃풋1(이진분류) = sigmoid, 아웃풋3(다중분류), softmax)

```
<span>model</span><span>.</span><span>add</span><span>(</span><span>Dense</span><span>(</span><span>3</span><span>,</span> <span>activation</span><span>=</span><span>"softmax"</span><span>))</span>
```

다.컴파일

이진분류 모델 (binary\_crossentropy)

```
<span>model</span><span>.</span><span>compile</span><span>(</span><span>optimizer</span><span>=</span><span>"adam"</span><span>,</span>
                       <span>loss</span><span>=</span><span>"binary_crossentropy"</span><span>,</span>
                       <span>metrics</span><span>=</span><span>[</span><span>"accuracy"</span><span>])</span>
```

다중분류 모델 (categorical\_crossentropy) (원핫인코딩 된 경우)

```
<span>model</span><span>.</span><span>compile</span><span>(</span><span>optimizer</span><span>=</span><span>"adam"</span><span>,</span>
                       <span>loss</span><span>=</span><span>"categorical_crossentropy"</span><span>,</span>
                       <span>metrics</span><span>=</span><span>[</span><span>"accuracy"</span><span>])</span>
```

다중분류 모델 (sparse\_categorical\_crossentropy) (원핫인코딩 안된 경우)

```
<span>model</span><span>.</span><span>compile</span><span>(</span><span>optimizer</span><span>=</span><span>"adam"</span><span>,</span>
                       <span>loss</span><span>=</span><span>"sparse_categorical_crossentropy"</span><span>,</span>
                       <span>metrics</span><span>=</span><span>[</span><span>"accuracy"</span><span>])</span>
```

예측 모델

```
<span>model</span><span>.</span><span>compile</span><span>(</span><span>optimizer</span><span>=</span><span>"adam"</span><span>,</span>
                       <span>loss</span><span>=</span><span>"mse"</span><span>)</span>
```

마. 딥러닝 테스트 핏

```
<span>model</span><span>.</span><span>fit</span><span>(</span><span>x</span><span>=</span><span>X_train</span><span>,</span> <span>y</span><span>=</span><span>y_train</span><span>,</span>
        <span>epochs</span><span>=</span><span>50</span><span>,</span> <span>batch_size</span><span>=</span><span>20</span><span>,</span>
        <span>validation_data</span><span>=</span><span>(</span><span>X_test</span><span>,</span> <span>y_test</span><span>),</span>
        <span>verbose</span><span>=</span><span>1</span><span>,</span>
        <span>callbacks</span><span>=</span><span>[</span><span>early_stop</span><span>,</span> <span>check_point</span><span>])</span>
```

조기종료 옵션 (케라스 조기종료&체크포인트 불러오기)

```
<span>from</span> <span>tensorflow.keras.callbacks</span> <span>import</span> <span>EarlyStopping</span><span>,</span> <span>ModelCheckpoint</span>
```

(조기종료 : 로스값이 올라가면(5번까지는 괜찮음) 조기종료하기)

```
<span>early_stop</span> <span>=</span> <span>EarlyStopping</span><span>(</span><span>monitor</span><span>=</span><span>"val_loss"</span><span>,</span> <span>mode</span><span>=</span><span>"min"</span><span>,</span>
                     <span>verbose</span><span>=</span><span>1</span><span>,</span> <span>patience</span><span>=</span><span>5</span><span>)</span>
```

(체크포인트 : 최적 로스값을 기억(best\_model.h5)하여 불러오기)

```
<span>check_point</span> <span>=</span> <span>ModelCheckpoint</span><span>(</span><span>"best_model.h5"</span><span>,</span> <span>verbose</span><span>=</span><span>1</span><span>,</span>
                       <span>monitor</span><span>=</span><span>"val_loss"</span><span>,</span> <span>mode</span><span>=</span><span>"min"</span><span>,</span> <span>save_best_only</span><span>=</span><span>True</span><span>)</span>
```

바. 학습과정 로그(loss,accuracy) history에 선언하여 남기기

```
<span>history</span> <span>=</span> <span>model</span><span>.</span><span>fit</span><span>(</span><span>x</span><span>=</span><span>X_train</span><span>,</span> <span>y</span><span>=</span><span>y_train</span><span>,</span>
        <span>epochs</span><span>=</span><span>50</span><span>,</span> <span>batch_size</span><span>=</span><span>20</span><span>,</span>
        <span>validation_data</span><span>=</span><span>(</span><span>X_test</span><span>,</span> <span>y_test</span><span>),</span>
        <span>verbose</span><span>=</span><span>1</span><span>,</span>
        <span>callbacks</span><span>=</span><span>[</span><span>early_stop</span><span>,</span> <span>check_point</span><span>])</span>
```

사. 학습로그 시각화 확인

```
<span>import</span> <span>matplotlib.pyplot</span> <span>as</span> <span>plt</span>
<span>plt</span><span>.</span><span>plot</span><span>(</span><span>history</span><span>.</span><span>history</span><span>[</span><span>"accuracy"</span><span>])</span>
<span>plt</span><span>.</span><span>plot</span><span>(</span><span>history</span><span>.</span><span>history</span><span>[</span><span>"val_accuracy"</span><span>])</span>
<span>plt</span><span>.</span><span>title</span><span>(</span><span>"Accuracy"</span><span>)</span>
<span>plt</span><span>.</span><span>xlabel</span><span>(</span><span>"Epochs"</span><span>)</span>
<span>plt</span><span>.</span><span>ylabel</span><span>(</span><span>"Accuracy"</span><span>)</span>
<span>plt</span><span>.</span><span>legend</span><span>([</span><span>"train_acc"</span><span>,</span> <span>"val_acc"</span><span>])</span>
<span>plt</span><span>.</span><span>show</span><span>(</span> <span>)</span>
```

아. 딥러닝 성능평가

```
<span>losses</span> <span>=</span> <span>pd</span><span>.</span><span>DataFrame</span><span>(</span><span>model</span><span>.</span><span>history</span><span>.</span><span>history</span><span>)</span>
<span>losses</span><span>[[</span><span>"loss"</span><span>,</span> <span>"val_loss"</span><span>]].</span><span>plot</span><span>(</span> <span>)</span>

<span>frome</span> <span>sklearn</span><span>.</span><span>metrics</span> <span>import</span> <span>classification_report</span><span>,</span> <span>confusion_matrix</span>
<span>predictions</span> <span>=</span> <span>model</span><span>.</span><span>predict_classes</span><span>(</span><span>X_test</span><span>)</span>
<span>print</span><span>(</span><span>classification_report</span><span>(</span><span>y_test</span><span>,</span> <span>predictions</span><span>))</span>
<span>print</span><span>(</span><span>confustion_matrix</span><span>(</span><span>y_test</span><span>,</span><span>predictions</span><span>))</span>
```

## RNN[](https://lovespacewhite.github.io/#rnn)

RNN 모델링

```
<span>import</span> <span>tensorflow</span> <span>as</span> <span>tf</span>
<span>from</span> <span>tensorflow.keras.models</span> <span>import</span> <span>Sequential</span>
<span>from</span> <span>tensorflow.keras.layers</span> <span>import</span> <span>Dense</span><span>,</span> <span>Flatten</span>
<span>from</span> <span>tensorflow.keras.layers</span> <span>import</span> <span>LSTM</span>

<span>X_train</span><span>.</span><span>shape</span><span>,</span> <span>X_test</span><span>.</span><span>shape</span>

<span>X_train</span> <span>=</span> <span>X_train</span><span>.</span><span>reshape</span><span>(</span><span>-</span><span>1</span><span>,</span><span>18</span><span>,</span><span>1</span><span>)</span>
<span>X_test</span> <span>=</span> <span>X_test</span><span>.</span><span>reshape</span><span>(</span><span>-</span><span>1</span><span>,</span><span>18</span><span>,</span><span>1</span><span>)</span>

<span>X_train</span><span>.</span><span>shape</span><span>,</span> <span>X_test</span><span>.</span><span>shape</span>

<span>model</span> <span>=</span> <span>Sequential</span><span>()</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>LSTM</span><span>(</span><span>32</span><span>,</span><span>activation</span><span>=</span><span>'relu'</span><span>,</span><span>return_sequences</span><span>=</span><span>True</span><span>,</span><span>input_shape</span><span>=</span><span>(</span><span>18</span><span>,</span><span>1</span><span>)))</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>LSTM</span><span>(</span><span>16</span><span>,</span><span>activation</span><span>=</span><span>'relu'</span><span>,</span><span>return_sequences</span><span>=</span><span>True</span><span>))</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>Flatten</span><span>)</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>Dense</span><span>(</span><span>8</span><span>,</span><span>activation</span><span>=</span><span>'relu'</span><span>))</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>Dense</span><span>(</span><span>1</span><span>,</span><span>activation</span><span>=</span><span>'sigmoid'</span><span>))</span>

<span>model</span><span>.</span><span>summary</span><span>()</span>

<span>model</span><span>.</span><span>compile</span><span>(</span>
 <span>optimizer</span><span>=</span><span>'adam'</span><span>,</span>
 <span>loss</span><span>=</span><span>'binary_crossentropy'</span><span>,</span>  <span>## 이진분류 : binary_crossentropy
</span> <span>metrics</span><span>=</span><span>[</span><span>'accuracy'</span><span>])</span>


<span>history</span> <span>=</span> <span>model</span><span>.</span><span>fit</span><span>(</span><span>x</span><span>=</span><span>X_train</span><span>,</span><span>y</span><span>=</span><span>y_train</span><span>,</span>
 <span>epochs</span><span>=</span><span>10</span><span>,</span>
 <span>batch_size</span><span>=</span><span>128</span><span>,</span>
 <span>validation_data</span><span>=</span><span>(</span><span>X_test</span><span>,</span><span>y_test</span><span>),</span>
 <span>verbose</span><span>=</span><span>1</span><span>)</span>

<span>losses</span> <span>=</span> <span>pd</span><span>.</span><span>DataFream</span><span>(</span><span>model</span><span>.</span><span>history</span><span>.</span><span>history</span><span>)</span>
<span>losses</span><span>.</span><span>head</span><span>()</span>
<span>losses</span><span>[[</span><span>'loss'</span><span>,</span><span>'val_loss'</span><span>]].</span><span>plot</span><span>()</span>

<span>losses</span><span>[[</span><span>'loss'</span><span>,</span><span>'val_loss'</span><span>,</span><span>'accuracy'</span><span>,</span><span>'val_accuracy'</span><span>]].</span><span>plot</span><span>()</span>

<span>plt</span><span>.</span><span>plot</span><span>(</span><span>history</span><span>.</span><span>history</span><span>[</span><span>'accuracy'</span><span>])</span>
<span>plt</span><span>.</span><span>plot</span><span>(</span><span>history</span><span>.</span><span>history</span><span>[</span><span>'val_accuracy'</span><span>])</span>
<span>plt</span><span>.</span><span>title</span><span>(</span><span>'Accuracy'</span><span>)</span>
<span>plt</span><span>.</span><span>xlabel</span><span>(</span><span>'Epochs'</span><span>)</span>
<span>plt</span><span>.</span><span>ylabel</span><span>(</span><span>'Acc'</span><span>)</span>
<span>plt</span><span>.</span><span>legend</span><span>([</span><span>'acc'</span><span>,</span><span>'val_acc'</span><span>])</span>
<span>plt</span><span>.</span><span>show</span><span>()</span>
```

## CNN[](https://lovespacewhite.github.io/#cnn)

가. 이미지 불러오기

```
<span>import</span> <span>os</span>
<span>from</span> <span>glob</span> <span>import</span> <span>glob</span>
<span>import</span> <span>tensorflow</span> <span>as</span> <span>tf</span>

<span>FILENAME</span> <span>=</span> <span>'dataset-new_old.zip'</span>
<span>glob</span><span>(</span><span>FILENAME</span><span>)</span>

<span>if</span> <span>not</span> <span>os</span><span>.</span><span>path</span><span>.</span><span>exists</span><span>(</span><span>'IMAGE'</span><span>)</span> <span>:</span>
 <span>!</span><span>mkdir</span> <span>IMAGE</span>
 <span>!</span><span>cp</span> <span>dataset</span><span>-</span><span>new_old</span><span>.</span><span>zip</span> <span>.</span><span>/</span><span>IMAGE</span>
 <span>!</span><span>cd</span> <span>IMAGE</span> <span>;</span> <span>unzip</span> <span>dataset</span><span>-</span><span>new_old</span><span>.</span><span>zip</span>

<span>new_img_path</span> <span>=</span> <span>'./IMAGE/new/plastic1.jpg'</span>
<span>gfile</span> <span>=</span> <span>tf</span><span>.</span><span>io</span><span>.</span><span>read_file</span><span>(</span><span>new_img_path</span><span>)</span>
<span>image</span> <span>=</span> <span>tf</span><span>.</span><span>io</span><span>.</span><span>decode_image</span><span>(</span><span>gfile</span><span>,</span><span>dtype</span><span>=</span><span>tf</span><span>.</span><span>float32</span><span>)</span>
<span>image</span><span>.</span><span>shape</span>
<span>plt</span><span>.</span><span>imshow</span><span>(</span><span>image</span><span>)</span>
<span>plt</span><span>.</span><span>show</span><span>()</span>

<span>old_img_path</span> <span>=</span> <span>'./IMAGE/old/old_plastic1.jpg'</span>
<span>gfile</span> <span>=</span> <span>tf</span><span>.</span><span>io</span><span>.</span><span>read_file</span><span>(</span><span>old_img_path</span><span>)</span>
<span>image</span><span>.</span><span>shape</span>
<span>plt</span><span>.</span><span>imshow</span><span>(</span><span>image</span><span>)</span>
<span>plt</span><span>.</span><span>show</span><span>()</span>

<span>Data</span> <span>Preprocess</span>

<span>num_epochs</span> <span>=</span> <span>50</span>
<span>batch_size</span> <span>=</span> <span>4</span>
<span>learning_rate</span> <span>=</span> <span>0.001</span>

<span>input_shape</span> <span>=</span> <span>(</span><span>384</span><span>,</span><span>512</span><span>,</span><span>3</span><span>)</span>  <span>## size
</span><span>num_classes</span> <span>=</span> <span>2</span>  <span>## new &amp; old
</span>
<span>from</span> <span>tensorflow.keras.preprocessing.image</span> <span>import</span> <span>ImageDataGenerator</span>

<span>training_datagen</span> <span>=</span> <span>ImageDataGenerator</span><span>(</span>
 <span>rescale</span> <span>=</span> <span>1.</span><span>/</span><span>255</span><span>,</span>
 <span>validation_split</span><span>=</span><span>0.2</span>  <span># train set : 435*(1-0.2)=348)
</span>
<span>test_datagen</span> <span>=</span> <span>ImageDataGenerator</span><span>(</span>
 <span>rescale</span> <span>=</span> <span>1.</span><span>/</span><span>255</span><span>,</span>
 <span>validation_split</span><span>=</span><span>0.2</span>  <span># test set : 435*0.2 = 87)
</span>
```

나. 이미지 읽기, 배치, 셔플, 레이블링

```
<span>!</span><span>rm</span> <span>-</span><span>rf</span> <span>.</span><span>/</span><span>IMAGE</span><span>/</span><span>.</span><span>ipynb_checkpoints</span> 

<span>training_generator</span>
<span>training_datagen</span><span>.</span><span>flow_from_directory</span><span>(</span>
 <span>',/IMAGE/'</span><span>,</span>
 <span>batch_size</span> <span>=</span> <span>batch_size</span><span>,</span>
 <span>target_size</span> <span>=</span> <span>(</span><span>384</span><span>,</span><span>512</span><span>),</span>  <span>## size
</span> <span>class_mode</span> <span>=</span> <span>'catrgorical'</span><span>,</span>  <span>## binary, categorical
</span> <span>shuffle</span> <span>=</span> <span>True</span><span>,</span>
 <span>subset</span> <span>=</span><span>'training'</span>  <span>## training, validation, validation_split 사용하므로 subset 지정
</span><span>)</span>

<span>test_generator</span>
<span>test_datagen</span><span>.</span><span>flow_from_directory</span><span>(</span>
 <span>',/IMAGE/'</span><span>,</span>
 <span>batch_size</span> <span>=</span> <span>batch_size</span><span>,</span>
 <span>target_size</span> <span>=</span> <span>(</span><span>384</span><span>,</span><span>512</span><span>),</span>  <span>## size
</span> <span>class_mode</span> <span>=</span> <span>'catrgorical'</span><span>,</span>  <span>## binary, categorical
</span> <span>shuffle</span> <span>=</span> <span>True</span><span>,</span>
 <span>subset</span> <span>=</span><span>'validation'</span>  <span>## training, validation, validation_split 사용하므로 subset 지정
</span><span>)</span>

<span>print</span><span>(</span><span>training_generator</span><span>.</span><span>class_indices</span><span>)</span>

<span>batch_samples</span> <span>=</span> <span>next</span><span>(</span><span>iter</span><span>(</span><span>traning_generator</span><span>))</span>

<span>print</span><span>(</span><span>'True Value : '</span><span>batch_sample</span><span>[</span><span>1</span><span>][</span><span>0</span><span>])</span>
<span>plt</span><span>.</span><span>imshow</span><span>(</span><span>batch_sample</span><span>[</span><span>0</span><span>][</span><span>0</span><span>])</span>
<span>plt</span><span>.</span><span>show</span><span>()</span>
```

다. CNN 모델링

```
<span>import</span> <span>tensorflow</span> <span>as</span> <span>tf</span>
<span>from</span> <span>tensorflow.keras.models</span> <span>import</span> <span>Sequential</span>
<span>from</span> <span>tensorflow.keras.layers</span> <span>import</span> <span>Dense</span><span>,</span> <span>Flatten</span><span>,</span> <span>Dropout</span>
<span>from</span> <span>tensorflow.keras.layers</span> <span>import</span> <span>Conv2D</span><span>,</span> <span>MaxPooling2D</span>

<span>model</span> <span>=</span> <span>Sequential</span><span>()</span>  <span>## Feature extraction
</span><span>model</span><span>.</span><span>add</span><span>(</span><span>Conv2D</span><span>(</span><span>filters</span><span>=</span><span>32</span><span>,</span><span>kernel_size</span><span>=</span><span>3</span><span>,</span><span>activation</span><span>=</span><span>'relu'</span><span>,</span><span>input_shape</span><span>=</span><span>input_shape</span><span>))</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>MaxPooling2D</span><span>(</span><span>pool_size</span><span>=</span><span>2</span><span>))</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>Conv2D</span><span>(</span><span>filters</span><span>=</span><span>16</span><span>,</span><span>kernel_size</span><span>=</span><span>3</span><span>,</span><span>activation</span><span>=</span><span>'relu'</span><span>))</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>MaxPooling2D</span><span>(</span><span>pool_size</span><span>=</span><span>2</span><span>))</span>

<span>model</span><span>.</span><span>add</span><span>(</span><span>Flatten</span><span>())</span>  <span>## Classfication
</span><span>model</span><span>.</span><span>add</span><span>(</span><span>Dense</span><span>(</span><span>50</span><span>,</span> <span>activation</span><span>=</span><span>'relu'</span><span>))</span>
<span>model</span><span>.</span><span>add</span><span>(</span><span>Dense</span><span>(</span><span>2</span><span>,</span> <span>activation</span><span>=</span><span>'softmax))

model.summary()

model.compile(
 optimizer='</span><span>adam</span><span>',
 loss='</span><span>categorical_crossentropy</span><span>',  ## 이진분류
 metrics=['</span><span>accuracy</span><span>'])

history = model.fit(training_generator,
 epochs=3,
 steps_per_epoch = len(training_generator) / batch_size,
 validation_steps = len(test_generator) / batch_size,
 validation_data = test_generator,
 vervose = 1
)
</span>
```

라. 성능평가/시각화

```
<span>losses</span> <span>=</span> <span>pd</span><span>.</span><span>Dataframe</span><span>(</span><span>model</span><span>.</span><span>history</span><span>.</span><span>history</span><span>)</span>
<span>losses</span> <span>=</span> <span>head</span><span>()</span>

<span>losses</span><span>[[</span><span>'loss'</span><span>,</span><span>'val_loss'</span><span>]].</span><span>plot</span><span>()</span>

<span>losses</span><span>[[</span><span>'loss'</span><span>,</span><span>'val_loss'</span><span>,</span><span>'accuracy'</span><span>,</span><span>'val_accuracy'</span><span>]].</span><span>plot</span><span>()</span>

<span>plt</span><span>.</span><span>plot</span><span>(</span><span>history</span><span>.</span><span>history</span><span>[</span><span>'accuracy'</span><span>])</span>
<span>plt</span><span>.</span><span>plot</span><span>(</span><span>history</span><span>.</span><span>history</span><span>[</span><span>'val_accuracy'</span><span>])</span>
<span>plt</span><span>.</span><span>title</span><span>(</span><span>'Accuracy'</span><span>)</span>
<span>plt</span><span>.</span><span>xlabel</span><span>(</span><span>'Epochs'</span><span>)</span>
<span>plt</span><span>.</span><span>ylable</span><span>(</span><span>'Acc'</span><span>)</span>
<span>plt</span><span>.</span><span>legend</span><span>([</span><span>'acc'</span><span>,</span><span>'val_acc'</span><span>])</span>
<span>plt</span><span>.</span><span>show</span><span>()</span>
```

마. 예측하기

```
<span># test_generator 샘플데이터 가져오기
# 배치사이즈 32 확인
</span><span>batch_img</span><span>,</span> <span>batch_label</span> <span>=</span> <span>next</span><span>(</span><span>iter</span><span>(</span><span>test_generator</span><span>))</span>
<span>print</span><span>(</span><span>batch_img</span><span>.</span><span>shape</span><span>)</span>
<span>print</span><span>(</span><span>batch_label</span><span>.</span><span>shape</span><span>)</span>

<span># 4개 test 샘플이지미 그려보고 예측해보기
</span><span>i</span> <span>=</span> <span>1</span>
<span>plt</span><span>.</span><span>figure</span><span>(</span><span>figsize</span><span>=</span><span>(</span><span>16</span><span>,</span><span>30</span><span>))</span>
<span>for</span> <span>img</span><span>,</span> <span>label</span> <span>in</span> <span>list</span><span>(</span><span>zip</span><span>(</span><span>batch_img</span><span>,</span> <span>batch_label</span><span>)):</span>
 <span>pred</span> <span>=</span> <span>model</span><span>.</span><span>predict</span><span>(</span><span>img</span><span>,</span><span>reshape</span><span>(</span><span>-</span><span>1</span><span>,</span><span>384</span><span>,</span><span>512</span><span>,</span><span>3</span><span>))</span>
 <span>pred_t</span> <span>=</span> <span>np</span><span>.</span><span>argmax</span><span>(</span><span>pred</span><span>)</span>
 <span>plt</span><span>.</span><span>subplot</span><span>(</span><span>8</span><span>,</span><span>4</span><span>,</span><span>i</span><span>)</span>
 <span>plt</span><span>.</span><span>title</span><span>(</span><span>f</span><span>'True Value:</span><span>{</span><span>np</span><span>.</span><span>argmax</span><span>(</span><span>label</span><span>)</span><span>}</span><span>, Pred Value:</span><span>{</span><span>pred_t</span><span>}</span><span>)
 plt.imshow(img)
 i = i + 1
</span>
```

___

## Stacking[](https://lovespacewhite.github.io/#stacking)

개별모델이 예측한 데이터를 기반한 종합예측

```
<span>from</span> <span>sklearn.ensemle</span> <span>import</span> <span>StackingRegressor</span><span>,</span> <span>StackingClassifier</span>

<span>stack_models</span> <span>=</span>
<span>[(</span><span>'LogisticRegression'</span><span>,</span><span>lg</span><span>),(</span><span>'KNN'</span><span>,</span><span>knn</span><span>),(</span><span>'DecisionTree'</span><span>,</span><span>dt</span><span>)]</span>

<span>stacking</span> <span>=</span> <span>StackingClassifier</span><span>(</span>
 <span>stack_models</span><span>,</span> <span>final_estimator</span><span>=</span><span>rfc</span><span>,</span><span>n_jobs</span><span>=-</span><span>1</span><span>)</span>

<span>stacking</span><span>.</span><span>fit</span><span>(</span><span>X_train</span><span>,</span><span>y_train</span><span>)</span>

<span>stacking_pred</span> <span>=</span> <span>stacking</span><span>.</span><span>predict</span><span>(</span><span>X_test</span><span>)</span>

<span>accuracy_eval</span><span>(</span><span>'Stacking Ensemble'</span><span>,</span> <span>stacking_pred</span><span>,</span> <span>y_test</span><span>)</span>
```

## Weighted Blending[](https://lovespacewhite.github.io/#weighted-blending)

각 모델 예측값에 대하여 weight를 곱하여 최종계산

```
<span>final_output</span> <span>=</span> <span>{</span>
 <span>'DecisionTree'</span><span>:</span><span>dt_pred</span><span>,</span>
 <span>'randomforest'</span><span>:</span><span>rf_pred</span><span>,</span>
 <span>'xgb'</span><span>:</span><span>xgb_pred</span><span>,</span>
 <span>'lgbm'</span><span>:</span><span>lgbm_pred</span><span>,</span>
 <span>'stacking'</span><span>:</span><span>stacking_pred</span>
<span>}</span>

<span>final_prediction</span><span>=</span>\
<span>final_outputs</span><span>[</span><span>'DecisionTree'</span><span>]</span><span>*</span><span>0.1</span>\
<span>+</span><span>final_outputs</span><span>[</span><span>'randomforest'</span><span>]</span><span>*</span><span>0.2</span>\
<span>+</span><span>final_outputs</span><span>[</span><span>'xgb'</span><span>]</span><span>*</span><span>0.25</span>\
<span>+</span><span>final_outputs</span><span>[</span><span>'lgbm'</span><span>]</span><span>*</span><span>0.15</span>\
<span>+</span><span>final_outputs</span><span>[</span><span>'stacking'</span><span>]</span><span>*</span><span>0.3</span>\

<span>final_prediction</span> <span>=</span> <span>np</span><span>.</span><span>where</span><span>(</span><span>final_prediction</span><span>&gt;</span><span>0.5</span><span>,</span><span>1</span><span>,</span><span>0</span><span>)</span> 
<span>## 가중치값이 0.5 초과하면 1, 그렇지 않으면 0
</span>
<span>accuracy_eval</span><span>(</span><span>'Weighted Blending'</span><span>,</span> <span>final_prediction</span><span>,</span> <span>y_test</span><span>)</span>
```

___

## \[4.성능평가\]

## 목표[](https://lovespacewhite.github.io/#%EB%AA%A9%ED%91%9C)

Loss(오차율) 낮추고, Accuracy(정확도) 높이기  
Error -> Epochs이 많아질수록 줄어들어야 함  
Epoch 많아질수록, 오히려 TestSet Error 올라가는경우 생길때, 직전Stop  
학습시 조기종료(early stop) 적용되지 않았을 때는 개선여지가 있기에,  
배치사이즈나 에포크를 수정하여 개선할 수 있음

## 좋은 모델[](https://lovespacewhite.github.io/#%EC%A2%8B%EC%9D%80-%EB%AA%A8%EB%8D%B8)

과적합(overfitting) : 선이 너무 복잡  
트레인 어큐러시만 높아지고, 벨리드 어큐러시는 높아지지 않을때 (트레인어큐러시에 맞춰짐)  
과소적합(underfitting) : 선이 너무 단순  
트레인/벨리드 어큐러시가 교차되지 않고 아직 수평선을 향해 갈때  
좋은모델 : 어느정도 따라가는 적당선  
트레인/벨리드 어큐러시가 수평선을 이어 서로 교차될때

## 성능지표[](https://lovespacewhite.github.io/#%EC%84%B1%EB%8A%A5%EC%A7%80%ED%91%9C)

오차행렬(Confusion Matrix) (분류모델에 주로 쓰임)

-   TP (True Positive)
-   TN (True Negative)
-   FP (False Positive)
-   FN (False Negative)

오차행렬 지표

-   정확도(Accuracy) = 맞춤(TP&TN) / 전체(total)
-   정밀도(Precision) = TP / TP + FP (예측한 클래스 중, 실제로 해당 클래스인 데이터 비율)
-   재현율(Recall) = TP = TP + FN (실제 클래스 중, 예측한 클래스와 일치한 데이터 비율)
-   F1점수(F1-score) = 2 \* \[1/{(1/Precision)+(1/Recall)}\] (Precision과 Recall의 조화평균)
-   Support = 각 클래스 실제 데이터수

오차행렬 성능지표 쉽게확인

```
<span>from</span> <span>sklearn.metrics</span> <span>import</span> <span>classification_report</span>
<span>print</span><span>(</span><span>classification_report</span><span>(</span><span>y_test</span><span>,</span> <span>y_pred</span><span>))</span>
```

오차행렬 성능지표 확인

```
<span>import</span> <span>seaborn</span> <span>as</span> <span>sns</span>
<span>from</span> <span>sklearn.metrics</span> <span>import</span> <span>confusion_matrix</span>
<span>from</span> <span>sklearn.metrics</span> <span>import</span> <span>precision_score</span><span>,</span> <span>recall_score</span>

<span>y_pred</span> <span>=</span> <span>model</span><span>.</span><span>predict</span><span>(</span><span>X_test</span><span>)</span>
<span>cm</span> <span>=</span> <span>confusion_matrix</span><span>(</span><span>y_true</span><span>=</span><span>y_test</span><span>,</span> <span>y_pred</span><span>=</span><span>y_pred</span><span>)</span>
```

```
<span>sns</span><span>.</span><span>heatmap</span><span>(</span><span>cm</span><span>,</span> <span>annot</span><span>=</span><span>True</span><span>)</span>
<span>plt</span><span>.</span><span>show</span><span>()</span>

<span>print</span><span>(</span><span>classification_report</span><span>(</span><span>y_test</span><span>,</span> <span>y_pred</span><span>))</span>

<span>precision_score</span><span>(</span><span>y_true</span><span>,</span> <span>y_pred</span><span>)</span>
<span>recall_score</span><span>(</span><span>y_true</span><span>,</span> <span>y_pred</span><span>)</span>
```

## 손실함수[](https://lovespacewhite.github.io/#%EC%86%90%EC%8B%A4%ED%95%A8%EC%88%98)

회귀모델 손실함수(Loss Function)

-   MSE(Mean Squared Error) : 실제에서 예측값 차이를 제곱, 합하여 평균 (예측)
-   MAE(Mean Absolute Error) : 실제값 빼기 예측값 절댓값의 평균
-   CEE(Cross Entropy Error) : 예측결과가 빗나갈수록 더큰패널티 부여 (분류)

분류모델 손실함수

-   Binary Cross Entropy (이진분류)
-   Multi Class Classfication (다중분류)

## 주요 지표[](https://lovespacewhite.github.io/#%EC%A3%BC%EC%9A%94-%EC%A7%80%ED%91%9C)

-   loss = MSE (학습시 사용한 loss function종류에 의해 결정) (작을수록 좋음)
-   error = 실제값 빼기 예측값의 평균 (작을수록 좋음)
-   MSE = 실제값 빼기 예측값 제곱의 평균 (작을수록 좋음)
-   MAE = 실제값 빼기 예측값 절댓값의 평균 (작을수록 좋음)
-   R2(결정계수) = 독립변수가 종속변수를 얼마나 잘설명하는지 (클수록 좋음)

## RMSE값 확인하기[](https://lovespacewhite.github.io/#rmse%EA%B0%92-%ED%99%95%EC%9D%B8%ED%95%98%EA%B8%B0)

___

## \[5.적용\]

___