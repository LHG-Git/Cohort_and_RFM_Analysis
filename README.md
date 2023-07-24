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

# 주문 상태
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
#### 정의
> * 코호트는 시간의 흐름에 따라 유사한 특성을 가진 사용자들의 집합

> * 코호트 분석은 사용자를 상호 배타적인 그룹으로 그룹화하고 그들의 행동은 시간의 경과에 따라 측정된다.

> * 코호트 분석은 고객들을 기준으로 초기 달(기준 달)에 얼마나 많은 고객이 구매를 했는지를 파악하고, 이후의 각 달에 해당 기준 달과 비교하여 추가 구매를 하는 고객 수를 살펴본다. 따라서 각 코호트 인덱스(월)는 해당 월에 기준 달로부터 얼마나 많은 고객이 추가 구매를 했는지를 나타낸다.

<br><br>

# 'InvoiceDate'와 'CohortMonth' 열 사이의 날짜 차이를 계산
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/7435b6e0-dcf2-42a5-ab2e-b12babf8e98a></h3>

* 날짜 차이를 30으로 나누어 월 단위로 변환

* dt.days를 통해 소수점을 버리고 정수형 데이터로 반환

* 정수형 데이터로 형변환

* 0은 첫 번째 달(기준 달)을 의미

<br>

#### 표 해석
* CohortMonth 2010-12-01(기준 달)
  
* 코호트 인덱스 1 (기준 달로부터 첫 번째 달 뒤, 2011년 1월): 기준 달 이후 첫 번째 달인 2011년 1월에는 341명의 고객이 추가 구매함
  
* 코호트 인덱스 2 (기준 달로부터 두 번째 달 뒤, 2011년 2월): 기준 달 이후 두 번째 달인 2011년 2월에는 339명의 고객이 추가 구매함
                                                     ...
* 코호트 인덱스 12 (기준 달로부터 열두 번째 달 뒤, 2011년 12월): 기준 달 이후 열한 번째 달인 2011년 11월에는 467명의 고객이 추가 구매함.

<br><br>

#### 전체 고객 중 활성 고객의 비율로 정의되는 유지율 계산
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/7e84df93-8b79-4e85-8a0a-42b81e981212></h3>

* 첫 번째 거래는 CohortIndex 0에 해당하기 때문에, 데이터의 첫번째 열을 코호트 크기로 사용

* 코호트 분석에서 'Retention'은 특정 기간에 첫 번째 구매를 한 고객들 중에서 그 이후에도 지속적으로 구매를 이어나가는 고객들의 비율을 나타냄

* 쉽게 말해, 초기에 구매한 고객들 중에서 재구매를 하는 고객들의 비율을 의미함




