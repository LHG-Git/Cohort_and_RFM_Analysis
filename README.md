# Cohort_and_RFM_Analysis
📈 전자상거래 고객 세분화 분석
<div align="center">
  <h1>📈 개인 프로젝트<br><br>
  👨🏽‍🤝‍👨🏻 전자상거래 고객 세분화 분석</h1>
</div>

<h4> 💭 Language : Python <br><br>
     📝 Library : Pandas, Numpy, Matplotlib <br><br>
     🛠  Tool : Google Colab <br><br>
     📅 진행기간 : 2023.03.23 ~ 2023.06.07</h4>
     
### 👨‍👦‍👦 팀원소개
<table>
<tbody>
  <tr>
    <td align="left"><img src="" width="20px;" alt=""/><br /><b>팀원 : 이희구</b></a><br /></td>
   <tr/>
</tbody>
</table>

<br>

# 🔊 프로젝트 개요
* 고객 세분화에는 많은 잠재적 이점이 존재

* 회사가 고객을 대상으로 하는 효과적인 전략을 개발하는 데 도움이 됨
  
* 이는 전체 제품 개발 주기, 예산 관리 관행 및 고객 대상 판촉 콘텐츠 제공 계획에 직접적인 영향을 미침
  
* 고객 세분화는 회사가 고객이 얼마나 비슷한지, 그들에게 중요한 것과 그렇지 않은 것을 이해하는 데에도 도움이 될 수 있음
  
* 이러한 정보는 다양한 고객 기반을 위한 개인화된 관련 콘텐츠를 개발하는 데 사용됨
  
<br><br>

# 💡 분석 기획
* 해양오염지수를 예측하고, 해양오염 문제를 미리 예방에 일조
  
* 2019~2020년 약 2년치의 해양환경측정 데이터를 활용하여 분석, EDA, 모델링 및 예측 수행, 프로젝트의 전체적인 흐름 및 아키텍처 구상
  
* 통계 분석, 머신러닝 등 다양한 분석 방법을 활용하여 해양오염지수 예측
  
<br><br>

# 🔥 목표
* 가치가 높은 고객 기반, 즉 성장 잠재력이 가장 높거나 수익성이 가장 높은 고객을 식별하는 것

* 고객 세분화의 통찰력은 맞춤형 마케팅 캠페인을 개발하고 전반적인 마케팅 전략 및 계획을 설계하는 데 사용됨

<br><br>

# 🔎 데이터 수집
|데이터셋|출처|
|------|:------:|
|온라인 소매 데이터|UCI Machine Learning Repository|
<br>


# 🔎 데이터 전처리
|전처리|방법|
|------|:-------------:|
|결측치 제거|약 25%가 Nan값으로 채워져 있는 컬럼 삭제|
|중복값 제거|5,225개의 중복값 삭제|

<br><br>

# 📊 EDA(탐색적 데이터 분석)
## 1) Top10 국가
<h3 align="center"><img src= "https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/5abf98ec-7c8b-4f99-b751-5f8a1cc2cc22"></h3>

* 영국이 90% 이상을 차지하는 것을 보여주고, 다른 나라는 3%에도 미치지 않는 것을 확인

* 따라서, 영국만 추출하여 분석 진행 
  
<br><br>

## 2) 고객과 상품
### 2-a) 총 제품 수(Stock code), 거래 수(InvoiceNo), 고객 수(CustomerID) 파악
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/72805b80-36c0-4469-b778-bba6c5bd882f></h3>

* 약 4,300명의 고객, 3,700개의 제품, 22,000건의 거래 건을 확인

<br><br>

### 2-b) 모든 거래에서 구매한 제품의 수를 확인
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/110061e7-676a-4678-b9e4-ca7c67694eac></h3>

##### Insights
* 하나의 제품만 구매한 고객이 있는가 하면, 여러 번 주문한 고객이 있음
  
* 접두사 C가 붙은 경우, 취소된 거래를 나타냄

<br><br>

### 2-c) 주문 상태
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/be3b198e-8fa4-4f70-9e09-79ae517d72ba></h3>

* 약 16.47% 의 주문이 취소됨
 
<br><br>

## 3) Stock Code (제품 코드)
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/b3b8c676-125f-447a-8caa-73d968d7e5de></h3>

* POST의 수가 가장 많고, 그 뒤로 M, C2가 뒤를 잇는다는 것을 확인

<br><br>

## 4) 총 구매 금액
### 4-a)
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/e1cbe6f4-cff7-43a2-8e2d-f557f05e3ebc></h3>

* 대부분 낮은 금액의 구매로 이루어진 것을 확인

<br><br>

### 4-b)
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/48d5eee7-49f4-4f05-bd20-db2aaac42804></h3>

* 영국을 제외한 국가들의 주문 수 확인

<br><br>

# 📄 코호트 분석
### 1) 정의
> * 코호트는 시간의 흐름에 따라 유사한 특성을 가진 사용자들의 집합

> * 코호트 분석은 사용자를 상호 배타적인 그룹으로 그룹화하고 그들의 행동은 시간의 경과에 따라 측정된다.

> * 코호트 분석은 고객들을 기준으로 초기 달(기준 달)에 얼마나 많은 고객이 구매를 했는지를 파악하고, 이후의 각 달에 해당 기준 달과 비교하여 추가 구매를 하는 고객 수를 살펴본다. 따라서 각 코호트 인덱스(월)는 해당 월에 기준 달로부터 얼마나 많은 고객이 추가 구매를 했는지를 나타낸다.

<br><br>

### 2) 열 생성 및 그룹화
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/4d17cbbb-c335-4620-a8a4-052393100f60></h3>

* 'CohortMonth'라는 열을 생성하여 각 거래의 InvoiceDate의 해당 월의 첫 번째 날짜를 사용하여 거래가 이루어진 월을 나타냄 

* 그런 다음, 각 고객별로 첫 번째 거래 월에 대한 정보를 추출하고 그룹화함

<br><br>

### 3) 최초 구매 후 재구매한 달
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/67475f09-e29d-44f4-b87b-9b6cb79ad171></h3>

* InvoiceMonth와 CohortMonth 열 사이의 차이를 월 수로 계산하여 CohortIndex를 구함
  
* CohortIndex는 초기 구매 후 재구매가 일어난 월에 대한 정보를 알려줌
  
* 즉, 고객이 최초 구매한 후 얼마나 지나서 재구매를 했는지를 나타내는 지표

<br><br>

### 4) 코호트 분석 매트릭스
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/7435b6e0-dcf2-42a5-ab2e-b12babf8e98a></h3>

* CohortMonth 및 CohortIndex별로 데이터를 그룹화하고 CustomerID 열에 집계하여 코호트 분석 매트릭스를 얻음
  
* 이를 통해 각 CohortMonth(고객들이 처음 구매한 월)와 CohortIndex(초기 구매 후 재구매한 월까지의 기간)에 따른 고객들의 그룹화된 데이터를 확인할 수 있음

* 이를 통해 해당 기간에 재구매한 고객들의 행동을 파악할 수 있음

<br><br>

#### 4-a) 표 해석
* CohortMonth 2010-12-01(기준 달)
  
* 코호트 인덱스 1 (기준 달로부터 첫 번째 달 뒤, 2011년 1월): 기준 달 이후 첫 번째 달인 2011년 1월에는 341명의 고객이 추가 구매함
  
* 코호트 인덱스 2 (기준 달로부터 두 번째 달 뒤, 2011년 2월): 기준 달 이후 두 번째 달인 2011년 2월에는 339명의 고객이 추가 구매함
                                                     ...
* 코호트 인덱스 12 (기준 달로부터 열두 번째 달 뒤, 2011년 12월): 기준 달 이후 열한 번째 달인 2011년 11월에는 467명의 고객이 추가 구매함.

<br><br>

### 5) 전체 고객 중 활성 고객의 비율로 정의되는 유지율 계산
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/7e84df93-8b79-4e85-8a0a-42b81e981212></h3>

* 첫 번째 거래는 CohortIndex 0에 해당하기 때문에, 데이터의 첫번째 열을 코호트 크기로 사용

* 코호트 분석에서 'Retention'은 특정 기간에 첫 번째 구매를 한 고객들 중에서 그 이후에도 지속적으로 구매를 이어나가는 고객들의 비율을 나타냄

* 쉽게 말해, 초기에 구매한 고객들 중에서 재구매를 하는 고객들의 비율을 의미함

<br><br>

### 6) Retention Rates
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/d0460328-a5cb-4d2d-82da-010e00926862></h3>

* 위의 유지율 히트맵에서 CohortMonth 2010–12–01에 대해 평균 ~35%의 유지율이 있으며 가장 높은 유지율은 11개월(49.3%) 후에 발생한다는 것을 알 수 있음

* 다른 모든 CohortMonths의 평균 유지율은 약 18–25%
  
<br><br>

# 📄 RFM 분류
### 1) 정의
> * RFM분석은 최근 거래(Recency), 작년에 수행한 거래 수(Frequency), 거래의 금전적 가치(Monetary)를 기준으로 각 고객의 가중치를 생성하여 할당한 후에, 고객별로 세그먼트를 하는 방식이다.

> * RFM분석은 가장 최근 고객은 누구였는지, 누가 우리가게에서 물건을 몇 번이나 구입했는지, 그리고 누구의 거래 총 가치는 얼마인지 등 이 모든 정보를 통해 고객이 기업에 얼마나 기여하는지 이해하는데 사용된다.

> * RFM값을 얻은 후 일반적인 방법은 각 메트릭에 사분위수를 만들고 필요한 순서를 할당하는 것이다.

<br><br>

### 2) 스냅샷 설정
> * RFM분석을 위해 분석을 수행하는 날짜인 'snapshot date'정의를 해야한다. 여기서는 스냅샷 날짜를 데이터에서 가장 높은 날짜+1로 정의했다.

> * 스냅샷은 RFM 메트릭을 계산하는 기준 시점이다.

<br><br>

#### 2-a) 세그먼트 분할
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/113b5a14-973c-4071-a72e-7ed44199a5f7></h3>

* 그런 다음 해당 데이터를 4개의 분위수 세그먼트로 나눔

* 이때 분위수는 [25%ile, 50%ile, 75%ile]에서 나눔
 
* 그리고 이러한 점수들을 RFM_Segment 열에 모아 넣었음

* 각 속성에 대해 점수(1, 2, 3, 4)를 할당하였음

* 여기서 R은 Recency(최근성), F는 Frequency(빈도), M은 Monetary Value(금액)를 나타냄

* 따라서 각 고객의 R, F, M 값에 해당하는 점수를 RFM_Segment 열에 할당하여 그룹화된 세그먼트를 만듬.

<br><br>

### 3) R, F, M 속성에 점수 할당
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/dcb1ea94-122b-439a-a266-4336a49e4eda></h3>

* 최근성 메트릭의 경우 가장 최근성 값이 가장 작은 고객에게 가장 높은 값인 4가 할당됨 (최신 고객이므로)

* 빈도 및 금액 메트릭의 경우 가장 높은 값인 4가 각각 상위 25% 빈도 및 금액 값을 가진 고객에게 할당됨

* 측정항목을 사분위수로 나눈 후 RFM 사분위수 측정항목을 합산하여 RFM_Score를 계산하고 문자열로 조합하여 RFM_Segment를 계산

<br><br>

### 4) RFM 점수를 기반으로 데이터를 그룹화한 후, 다양한 RFM 점수에 대해 평균 속성 값을 비교
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/6d0665f6-e3f6-41e3-80b5-fe4135e96e30></h3>

* 예상대로 RFM 점수가 가장 낮은 고객은 최근성이 가장 높고, 빈도 및 금전적 가치가 가장 낮음

<br><br>

### 5) 범주 정의
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/563a3e1a-70e0-4856-85ac-56aa164eed01></h3>

* RFM_Score가 9 이상인 고객은 '상위' 범주
  
* RFM_Score가 5~9 사이인 고객은 '중간' 범주
  
* RFM_Score가 나머지인 고객은 '낮음' 범주

### 6) 왜도 제거
* RFM 점수에서 Kmeans 클러스터링을 위한 데이터를 준비할 것들
  
> * 변수는 대칭적으로 분포되어야 한다.
> * 변수는 평균값이 유사해야 한다.
> * 변수는 표준편차 값이 유사해야 한다.

<br><br>

<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/6b5cb92a-c0e8-4531-84ff-5c99f03f0756></h3>

* 안타깝게도 모든 변수는 대칭이 아님, 모두 오른쪽으로 치우쳐져있기 때문에, 왜도를 제거할 필요가 있음
  
* 왜도는 분포의 비대칭 정도를 측정하는 지표로서, 변수의 분포가 얼마나 대칭이 아닌지를 나타냄, 왜도는 주로 데이터의 분포를 확인하고 이상치를 탐지하거나 변수 변환을 위해 사용됨

<br><br>

#### 6-a) 왜도의 값에 따라 분포의 특성 해석
* 왜도 값이 0에 가까울 경우: 데이터의 분포가 대칭에 가까움을 의미

* 왜도 값이 0보다 큰 양수일 경우: 오른쪽으로 치우친 분포를 가진 양의 왜도를 가짐. 오른쪽으로 꼬리가 긴 분포를 의미

* 왜도 값이 0보다 작은 음수일 경우: 왼쪽으로 치우친 분포를 가진 음의 왜도를 가짐. 왼쪽으로 꼬리가 긴 분포를 의미

> * 왜도 값을 확인하여 변수가 대칭인지 아닌지를 파악하고, 대칭이 아닌 경우 데이터 변환을 고려할 수 있다. 로그 변환, 제곱근 변환, Box-Cox 변환 등을 사용하여 데이터를 변환하면 대칭성을 높일 수 있다. 이를 통해 분석의 정확성을 높이고 모델의 성능을 개선할 수 있다.

<br><br>

#### 6-b) 로그 변환을 통한 왜도 제거
##### b-1) 로그 변환
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/10a431d6-2dfc-412b-98e9-aa7724541234></h3>

* 로그 변환을 수행하고 날짜를 표준화

<br><br>

##### b-2) 왜도 제거
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/7dd4ad0a-e1c6-434f-babe-5ee698b0875b></h3>

<br><br>

### 7) K-means Clustering
#### 7-a) Elbow Method
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/a3a6c1bc-6496-4ae0-bb17-7bce248bc548></h3>

* 최적의 K값 3, 4, 5를 구함

<br><br>

#### 7-b) K = 3, 4, 5 각 값에 대한 세그먼트 해석
![image](https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/78453fd4-f4e3-441c-9185-52f2dae89150)





