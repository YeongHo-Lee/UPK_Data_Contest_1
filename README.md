# UPK_Data_Contest_1

- Member
  - 고영진
  - 이영호
  - 김지원
  - 차은비

# 1. Overview

## 제공되는 데이터 및 문서
- trainSet.csv  
자유롭게 학습에 사용할 수 있는 총 280 개 셰일가스 생산정 데이터  
  
- examSet.csv  
경진대회 문제용 45 개 셰일가스 생산정 데이터  
  
- 용어 정리.pdf  
trainSet.csv 기준으로 데이터 항목에 대한 설명 문서

## Goal

### 가스 생산량 예측

**<center>examSet.csv 에 주어진 45 개 셰일가스 생산정의 향후 6 개월 월 평균 가스생산량을 예측하시오</center>**

예측 정확도 평가 기준은 **sMAPE(symmetric mean absolute percentage error)** 으로 한다.

$sMAPE = {100\% \over n}\sum_{i=1}^n {|F_i-A_i| \over (|f_i| + |A_i|)/2}$

$𝐹_i$: i 번째 생산정의 향후 6 개월 월 평균 가스 생산량 예측 값  
$𝐴_i$: i 번째 생산정의 향후 6 개월 월 평균 가스 생산량 실제 값  
$𝑛$ : 예측 대상이 되는 생산정의 수 (이 문제에서는 45 개)  



### 생산정 투자 의사결정

**<center>$15,000,000 의 예산으로 examSet.csv 에 주어진 45 개의 셰일가스 생산정 중 일부를 구입하여 수익을 최대화 하시오.</center>**  

이 때 수익은 수입한 셰일가스생산정에서 향후 6 개월간 생산되는 셰일가스의 판매대금에서 각 생산정의 고정 운영 비용을 제외한 금액으로 정의한다.  

$$
PROFIT = \sum_{i=1}^n(6A_iP_s-P_i -Ci)X_i
$$

$𝐴_i$: i 번째 생산정의 향후 6 개월 월 평균 가스 생산량 실제 값  
$𝑃_i$: i 번째 생산정의 가격  
$𝑃_S$: 셰일가스 기준 가격 (1 Mcf 당 $5)  
$𝐶_i$: i 번째 생산정의 고정 운영 비용  
$𝑋_i$: i 번째 생산정 구입 여부 (구입 하면 $𝑋_i$ = 1, 구입하지 않으면 $𝑋_i$ = 0)  
이 때 아래와 같은 제약식이 추가된다.  
  
$$
\sum_{i=1}^nX_iP_i \leq X
$$
  
여기서 X 는 전체 예산($15,000,000)이므로, 위 제약식은 본 문제를 통해
구입하기로 결정한 생산정 구입을 위해 투입되는 금액의 총액이 전체
예산보다는 작아야한다는 것을 의미한다.
