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


# 🔎 데이터 수집
|데이터셋|출처|
|------|:------:|
|온라인 소매 데이터|UCI Machine Learning Repository|
<br>


# 🔎 데이터 전처리
|전처리|방법|
|------|:-------------:|
|결측치 제거|약 25%가 Nan값으로 채워져있기 때문에 해당 컬럼 삭제|
|중복값 제거(MinMaxScaler)|5,225개의 중복값 삭제|

<br><br>

# 📊 EDA(탐색적 데이터 분석)
## 1) Top10 국가
<h3 align="center"><img src= "https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/5abf98ec-7c8b-4f99-b751-5f8a1cc2cc22"></h3>

* 영국이 90% 이상을 차지하는 것을 보여주고, 다른 나라는 3%에도 미치지 않는 것을 확인

* 따라서, 영국만 추출하여 분석 진행 
  
<br>

## 2) 고객과 상품
### 2-a) 총 제품 수(Stock code), 거래 수(InvoiceNo), 고객 수(CustomerID) 파악
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/72805b80-36c0-4469-b778-bba6c5bd882f></h3>

* 약 4,300명의 고객, 3,700개의 제품, 22,000건의 거래 건을 확인

<br>

### 2-b) 모든 거래에서 구매한 제품의 수를 확인
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/110061e7-676a-4678-b9e4-ca7c67694eac></h3>

##### Insights
* 하나의 제품만 구매한 고객이 있는가 하면, 여러 번 주문한 고객이 있음
  
* 접두사 C가 붙은 경우, 취소된 거래를 나타냄

<br> 

<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/be3b198e-8fa4-4f70-9e09-79ae517d72ba></h3>

* 약 16.47% 의 주문이 취소됨
 
<br>

## 3) Stock Code
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/b3b8c676-125f-447a-8caa-73d968d7e5de></h3>

* POST의 수가 가장 많고, 그 뒤로 M, C2가 뒤를 잇는다는 것을 확인

<br>

## 4) 총 구매 금액
### 4-a
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/e1cbe6f4-cff7-43a2-8e2d-f557f05e3ebc></h3>

* 대부분 낮은 금액의 구매로 이루어진 것을 확인

<br>

### 4-b
<h3 align="center"><img src= https://github.com/LHG-Git/Cohort_and_RFM_Analysis/assets/100845169/48d5eee7-49f4-4f05-bd20-db2aaac42804></h3>

* 영국을 제외한 국가들의 주문 수 확인

<br><br>

# 📄 Modeling
## 1) 군집화
<h3 align="center"><img src= https://github.com/LHG-Git/project/assets/100845169/e22674c7-b20e-4298-b8bc-b7b9f2f4583a></h3>

* 최적의 k값 도출을 위해 <strong>실루엣 계수</strong>를 사용<br> 
* 이때 실루엣 계수 평균만을 고려하지 않았고 figure5를 통해 도출된 인사이트를 함께 고려<br>
* 그 결과 cluster별 실루엣 계수 평균이 가장 높지는 않지만, 실루엣 계수의 너비가 비교적 균일한 지점에서 <strong>최적의 k(k=6)값을 도출</strong><br><br>

<h3 align="center"><img src= https://github.com/LHG-Git/project/assets/100845169/909e7b1d-0b40-4745-abc5-f3652ef06a84></h3>

* 최적의 K값을 통해 위치별 군집화 결과, figure 5에서 인천 부근의 서해에 위치한 관측치와, 부산 부근의 남해에 위치한 관측치에서 화학적 산소농도 수치가 높게 기록
<br>

## 2) 모델 성능 지표 선정
* 성능 지표의 경우 본 프로젝트의 주제 자체가 ‘해양정보를 활용한 해양오염 예측’이기 때문에, 모델의 설명력을 나타내는 R2값 보다 실제 예측 오차의 크기인 MAE가 본 프로젝트와 맞는 지표라고 생각하여, <strong>MAE값을 기준으로 최종 모델을 선정</strong>
<br>

## 3) 최종 모델 선정
<h3 align="center"><img src= https://github.com/LHG-Git/project/assets/100845169/da4b5525-0513-4615-a954-9778eadeda55></h3>

* 최종 예측결과 전체 모델에서 훈련세트에 <strong>약간의 과적합 존재</strong><br>
* <strong>CatBoost모델의 MAE값이 가장 준수</strong>
* 해양오염 예측에 사용될 모델을 <strong>CatBoostRegressor로 선정</strong>
<br>

## 4) 하이퍼파라미터 튜닝
* CatBoostRegressor모델의 특성상 하이퍼파라미터 튜닝을 진행하여도 모델 성능 개선에 크게 영향을 미치지 않음
* 오히려 파라미터의 default값으로 모델 예측을 수행하였을 때, 성능이 가장 높게 측정됨
<br>

## 5) K-Fold 교차검증
* 최종 선정된 모델(CatBoostRegressor)의 경우 train과 text의 성능 지표에서 약간의 과적합이 발생
* 과적합을 방지하기 위해 valid data를 생성
* 해당 데이터셋을 이용하여 가장 흔하게 사용되는 <strong>K-Fold 교차검증을 진행</strong>
* <strong>K값은 5로 지정</strong>하였으며, 모델 진행시에 골고루 데이터의 특성을 반영하기 위하여 <strong>shuffle을 진행</strong>
<br>

## 6) 모델평가 및 검증
<h3 align="center"><img src= https://github.com/LHG-Git/project/assets/100845169/1f3ca8e2-9710-404d-9425-d9a9d3f64cdf></h3>

* <strong>하이퍼파라미터 튜닝 및 K-Fold교차검증을 통하여 모델 성능 최적화를 진행하여 과적합 개선</strong>

* 그 결과 이전의 결과에서 보다 <strong>과적합이 많이 개선</strong>되었음을 확인하였고 <strong>모델의 성능 또한 향상됨</strong>

* 성능 지표의 경우 본 프로젝트의 주제가 ‘해양정보를 활용한 해양오염 예측’ 이기 때문에, 모델의 설명력을 나타내는 R2값 보다 실제 예측 오차의 크기인 MAE가 본 프로젝트와 맞는 지표라고 판단

* <strong>최종 모델링 결과 약 MAE = 0.076으로 실제값과 약 0.076이 차이가 나는 모델 완성</strong>

* 최근 10년동안 국내 연안의 화학적 산소농도가 연평균 1.13~1.82mg/L인 것을 고려했을 때, 꽤 정확도가 높은 모델이라고 설명할 수 있음



