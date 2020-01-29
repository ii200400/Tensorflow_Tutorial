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

---

+ 

---
### 예시 코드

1.15.0 버전 : 

2.1.0-rc1 버전 : 

---

