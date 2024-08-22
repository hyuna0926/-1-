# 서울시 1인가구가 살기 좋은 동네 찾기
- 기간: 2023.01.02~01.16
- 언어: Python
- Project manage: Tableau

### 프로젝트 개요

수도권 중 특히 서울은 면적에 비해 1인 가구가 많이 분포해있습니다. 20-40대 1인 가구는 첫 독립일 확률이 높기 때문에 어떤 곳이 좋고 월세가 어느 정도인지 알 수 없을 것입니다. 그래서 데이터 분석을 통해 서울시에서 1인 가구가 살기 좋은 동네를 확인하려고 합니다. 

또한  첫 자취인 만큼 월세가 어느 정도인지 모르니 사기 당하지 않을 수 있게 1인 가구가 가장 많이 주거하는 원룸, 빌라, 오피스텔의 월세를 예측하고 싶어 직방 데이터를 크롤링해 서울시 행정구역별 월세를 예측하는 모델을 만들었습니다.

### 데이터 분석

통계청, 서울 열린데이터 광장에서 데이터를 다운받아 데이터 분석을 진행했습니다. 

1. 1인가구의 안전 만족도
2. 많이 거주하는 서울시 행정구
3. 5대 범죄가 많이 발생된 행정구
4. cctv가 많은 행정구
5. 유흥업소가 많은 행정구

### 가설검정

1. 인구수와 범죄 발생 간의 관계
2. 범죄 발생과 CCTV 간의 관계
3. 유흥업소와 범죄 발생간의 관계

### 인사이트 도출

위의 결과를  토대로 서울시에서 살기 좋은 동네는 **동북권**을 추천합니다. 동북권 중 **성동구, 강북구, 도봉구, 광진구**는 범죄 발생 수가 낮고 유흥업소도 적은 것으로 나타납니다.
그리고 조심해야 하는 동네는 **강남구, 관악구, 양천구** 등이 있습니다.

### 예측모델

직방에서 서울시 원룸, 빌라, 오피스텔 월세를 크롤링을 진행하였습니다. 
예측에 사용할 feature는 자치구, 보증금, 분류, 평수(평) 입니다. 총 13,872개의 데이터를 사용했습니다.<br> 
데이터의 속성을 고려해 회귀트리를 사용했습니다. 총 5개의 회귀트리모델을 이용했으며, 과적합을 방지하기 위해 K-Fold 교차검증을 사용하였습니다. 최종적으로 R2가 0.709인 LightGBM을 선택했습니다.
