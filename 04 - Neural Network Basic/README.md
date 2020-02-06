# 신경망 구현

## 딥러닝 기본 개념

+ 인공신경망(artificial neural network) : 인간의 뇌인 뉴런을 모방하여 만든 일련의 계산과정
  + 입력(y)을 받아서 가지고 있던 가중치(W), 편향(B), 활성화 함수(sigmoid)에 따라서 출력을 하는 인공신경들의 다발이다.\
  y = S (X * W + B)
  + 뉴런(neuron) : 인간의 신경에 존재하면서 신호를 전달하는 세포
  + 학습(learning) / 훈련(train) : 가중치와 편향의 적절한 값을 찾아가는 과정
  + 활성화 함수(activation function) : 인공 뉴런의 핵심 중 하나이다.
    + ex) Sigmoid(시그모이드), ReLU(렐루), Adam(아담) 등
    
+ 역전파(backpropagation) : 신경망이 학습을 할 때 적절한 가중치나 편향의 값을 찾아내도록 하는 계산 방법

## 역전파

딥러닝의 필수요소이며 계산이 오래걸리는 요인 중 하나로 개념은 오래전부터 존재했지만 컴퓨터 성능의 부족으로 현재에 와서 재조명된 알고리즘이다.

전파는 출력을 계산하기 위한 방법이고 (위의 y = S (X * W + B) 식이 해당됨)\
역전파는 가중치와 편향을 계산하기 위한 방법이다. (식이 어려우므로 생략, 자세한 내용은 구글링하면 많이 나온다.)

둘을 자세히 알기 위해서 미적분의 미분과 적분의 개념만 알아도 이해가 가능하다.\
하지만 구구단은 알지만 1234\*5678을 쉽게 계산하기 어려운 것처럼 계산량이 압도적이라서\
정말 간단한 인공신경망이 아니면 역전파 계산하기가 쉽지 않다;

하지만 한번은 꼭 개념을 잡고 가는 것을 추천하며 알고 있어도 다시 보는 것을 권장한다.

이런 어려운 인공신경망보다 더 대단한 내 뇌는 참 똑똑한 것 같다 :)

## 분류 모델 실습

딥러닝은 다양한 분야에서 쓰는데 그 중에서도 가장 인기가 있는 주제 중 하나인 패턴 인식을 통한 영상처리 모델이 있다.

실재로 이미지를 넣고 바로 분류를 해보면 좋겠으나 '분류'에만 초점을 두어 이미지대신 간단한 데이터로 분류 모델을 만들어보겠다.

+ 분류(classification) : 패턴이나 특징을 파악하여 종류를 구분하는 작업

---
### 예시 코드

1.15.0 버전 : https://colab.research.google.com/drive/1kBvwq70uanYLCBzgkzvvHCMZC2mA7hwD

2.1.0-rc1 버전 : https://colab.research.google.com/drive/1F0mwAi3HziD-g_7mxV_4Z75KMZ9JUlHQ

---