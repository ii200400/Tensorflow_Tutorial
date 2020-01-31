# 텐서플로 프로그래밍을 위한 기본기

## 텐서플로의 자료형과 작동방식

+ 텐서(tensor) : 텐서플로에서 다양한 수학식을 계산하기 위한 가장 기본적이고 중요한 자료형, 일반적인 배열의 형태와 비슷하다.
  + 랭크(rank) : 텐서의 차원의 수를 나타낸다. \
  랭크가 0이면 스칼라, 1이면 벡터, 2이면 행렬, 3 이상이면 n-Tensor 또는 n차원 텐서라고 한다.
  + 셰이프(shape) : 텐서의 크기를 나타낸다.
  + 예시\
  3 - 랭크는 0, 셰이프가 []인 텐서\
  [1,2,3] - 랭크는 1, 셰이프가 [3]인 텐서\
  [[1,2,3],[1,2,3]] - 랭크는 2, 셰이프가 [2,3]\
  [[[1,2,3]],[[1,2,3]]] - 랭크는 3, 셰이프가 [2,1,3]
  + dtype : 텐서에 담긴 데이터의 자료형
  + numpy : 텐서에 담긴 데이터의 값
  
+ 그래프 : 텐서들의 연산에 관한 모음을 의미한다.
+ 지연 실행(lazy evaluation) : 텐서나 그래프를 정의하는 것과 실행이 분리되어 있는 방식을 말한다.
  1. 먼저 텐서들의 그래프를 만든다.
  2. 원하는 시점에 그래프를 실행한다.

**웃기게도 텐서플로 2.x에서는 이러한 부분이 생략되어 훨씬 더 파이썬스러운 코드를 만들수 있게 되었다.**

---
### 예시 코드

1.15.0 버전 : https://colab.research.google.com/drive/13H2DStRYd34deZXswreup8aozAuDu5K7

2.1.0-rc1 버전 : https://colab.research.google.com/drive/126YC40UlpahkIdhpG2YYYi2YvYSx-ZCI

---

+ 플레이스홀더(placeholder) : 그래프에 사용할 입력값을 저장하는 매개변수와 같은 역할
+ 변수(variable) : 그래프를 최적화하는 용도, 텐서플로의 학습 함수들이 학습한 결과를 갱신하고 저장하는 역할

---
### 예시 코드

1.15.0 버전 : https://colab.research.google.com/drive/1h1DP4MrjduyEQrfcliuqy62MZ923PoDG

2.1.0-rc1 버전 : https://colab.research.google.com/drive/1Dwf8rm5uPNcVZ64gxDiRSwnqFYMcvBWT

## 선형 회귀 모델을 통한 실습

우선 딥러닝에 관한 기초적인 단어를 아래의 식을 예시로 하여 정리하겠다.

> y = Wx + b

+ 선형 회귀(Linear Regression) : 입력값(x)과 결과값(y)을 통하여 둘의 선형 상관 관계(y = Wx + b)를 알아내는 것을 의미한다.
+ 균등분포(uniform distribution) : 일정구간 내의 값들이 나타날 가능성이 동일한 분포이다.
+ 가중치(weight) : W를 의미한다. 결과값이 입력값에 얼마나 의존하는지를 의미한다.
+ 편향(bias) : b를 의미한다. 결과값이 얼마나 쉽게 활성화(0이상)되도록 하는지를 의미한다.
  + http://blog.daum.net/_blog/BlogTypeView.do?blogid=0K6Pu&articleno=6271145&_bloghome_menu=recenttext
  + https://sacko.tistory.com/10 3.가중치와 편향에서 자세하게 설명하였다.
+ 손실함수(loss function) : 잠시 저장했다가 다시 시작하겠다.
+ 비용(cost) :
+ 학습 : 

---
### 예시 코드

1.15.0 버전 : 

2.1.0-rc1 버전 : 

---

