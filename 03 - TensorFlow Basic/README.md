# 텐서플로 프로그래밍을 위한 기본기

아무리 전공자라고 할지라도 머신러닝이나 텐서플로우에 관한 단어는 들어본적이 없는 내용이 많다.\
때문에 관련 용어나 단어들은 볼 때마다 어떤 의미이고 어떻게 쓰이는지 확인하는 것이 좋다.

https://developers.google.com/machine-learning/glossary?hl=ko \
위의 링크는 텐서플로 용어집이다.\
약간 번역기스러운 문법과 난해한 단어들이 많지만 보다 정확한 정의를 간단하게 볼 수 있다.

## 텐서플로의 자료형과 작동방식

+ 텐서(tensor) : 텐서플로우 프로그램의 가장 기본적이고 중요한 자료형, 일반적인 배열의 형태와 비슷하다.
  + 랭크(rank) : 텐서의 차원의 수를 나타낸다. \
  랭크가 0이면 스칼라, 1이면 벡터, 2이면 행렬, 3 이상이면 n-Tensor 또는 n차원 텐서라고 한다.
  + 셰이프(shape) : 텐서의 요소의 수를 나타낸다.
  + 예시\
  [1,2,3] - 랭크는 1, 1차원에서 3인 셰이프\
  [[1,2,3],[1,2,3]] - 랭크는 2, 1차원에서 2, 2차원에서 3인 셰이프가 [2,3]\
  [[[1,2,3]],[[1,2,3]]] - 랭크는 3, 1차원에서 2, 2차원에서 1인, 2차원에서 3인 셰이프
  + dtype : 텐서에 담긴 데이터의 자료형
  + numpy : 텐서에 담긴 데이터의 값
  
+ 그래프(graph) : 텐서들의 연산에 관한 모음을 의미한다. 
+ 지연 실행(lazy evaluation) : 텐서나 그래프를 정의하는 것과 실행이 분리되어 있는 방식을 말한다.
  1. 먼저 텐서들의 그래프를 만든다.
  2. 원하는 시점에 그래프를 실행한다.

**웃기게도 텐서플로 2.x에서는 그래프와 부분이 생략되어 훨씬 더 파이썬스러운 코드를 만들수 있게 되었다.**

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

---

## 선형 회귀 모델을 통한 실습

우선 딥러닝에 관한 기초적인 단어를 아래의 식을 예시로 하여 정리하겠다.

> y = Wx + b

+ 선형 회귀(Linear Regression) : 회귀 모형의 한 유형으로 입력값(x)과 결과값(y)을 통하여 둘의 선형 상관 관계(y = Wx + b)로 연속적인 값을 출력한다.
+ 회귀 모형(regression model) : 연속 값을 출력하는 모델 유형이다. 
+ 분류 모델(classification model) : 둘 이상의 불연속 클래스를 구분 짓는 데 사용되는 머신러닝 모델 유형이다.\
개나리', '진달래' 같은 클래스들을 분류하여 출력한다.

+ 모델(model) : 머신러닝 기술로 학습 데이터를 활용하여 학습한 텐서플로우 그래프, 가중치 및 편향 등을 의미한다.
+ 균등분포(uniform distribution) : 일정구간 내의 값들이 나타날 가능성이 동일한 분포이다.
+ 가중치(weight) : W를 의미한다. 결과값이 입력값에 얼마나 의존하는지를 의미한다.
+ 편향(bias) : b를 의미한다. 결과값이 얼마나 쉽게 활성화(0이상)되도록 하는지를 의미한다.
  + 아래의 링크들을 참고하자.\
  http://blog.daum.net/_blog/BlogTypeView.do?blogid=0K6Pu&articleno=6271145&_bloghome_menu=recenttext \
  https://sacko.tistory.com/10 \
  (인공신경망 알고리즘을 퍼셉트론이라고 하는데 그에 대한 이야기를 쉽게 설명하였다.)

+ 손실함수(loss function) : 데이터의 손실값을 계산하기 위한 수식 또는 함수이며 일반적으로 (y-y`)\*\*2이다.
+ 손실값 : 실재값과 예측값(수식과 사용자가 준 x 데이터를 토대로 나온 결과값)의 차이를 나타내는 값이다.\
값이 작을수록 학습이 잘 되어 예측을 잘하고 있다는 의미로 받아들여진다.\
+ 비용(cost) : 손실과 같은 의미이다.
+ 학습(train) : 다양한 데이터를 넣어 손실값을 줄여나가 가장 최적화된(잘 예측을 하는) 모델을 결정하는 과정
+ 최적화(Optimization) : 변수들(W와 b)을 조정하여 손실값을 최소화하는 변수(W와 b)를 찾는 것이다. 
+ 경사하강법(gradient descent) : 최적화 방법 중 하나로 비용함수의 기울기가 0이 되는 방향으로 변수들을 조정한다.\
정말 간단한 최적화 방식이므로 일차함수와 같은 간단한 수식이 아니라면 해당 방식은 잘 사용하지 않는다. 
  + 학습률(learning rate) : 경사하강법을 이용한 최적화를 할 때 변수 변화율의 정도를 결정한다.
  + 하이퍼파라미터(hyperparameter) : 학습에 영향을 미치는 **사용자가 조절가능한** 변수를 의미한다. 위의 학습률도 이것이다.\
  하이퍼파라미터의 설정에 따라서 학습 속도나 신경망의 성능이 크게 달라질 수 있다.\
  위의 이유로 이것을 조정하는 것을 '하이퍼파라미터를 튜닝(tuning)한다'라고 한다.
  + 아래의 링크에서 사진을 참고하면 경사하강법을 이해하는데 도움이 된다. 단, 내용은 어려운 편이다.\
  https://jaehyeongan.github.io/2019/04/23/%EA%B2%BD%EC%82%AC%ED%95%98%EA%B0%95%EB%B2%95-Gradient-Descent/

---
### 예시 코드

1.15.0 버전 : https://colab.research.google.com/drive/1Q1K7F6XaFInyV9wKsIM5bYzergooA7Wh

2.1.0-rc1 버전 : https://colab.research.google.com/drive/1svvVL-iANx3-r3uxJ2u05yNftTASq4Lf#scrollTo=tkEp9jeknl2j

*바뀐 문법이 많아서 잘 변환하였는지 확신이 서지 않는다. 참고만 하도록 하자.*

---
