# 자연어 인식의 기본, RNN

한국어로 순환 신경망이라고 하는 RNN(Recurrent Neural Network)은 자연어나 음성과 같은 순서가 중요한 데이터를 처리하는데 강한 신경망이다.\
구글의 기계번역 또한 이 모델을 기반으로 만든 것이라고 한다.

이번 장에서는 음성, 자연어를 처리하는 RNN의 기본적인 사용법과 간단한 번역 프로그램을 만들 것이다.

## RNN 기본개념

기본 개념 참고 링크\
https://wikidocs.net/22886

셀(cell) : 은닉층에서 활성화 함수를 통해 결과를 내보내는 역할한다. 
  + 이전의 값을 기억하려고 하는 일종의 메모리 역할을 수행하기 때문에 메모리 셀 혹은 RNN 셀이라고 한다.
  + 이전 시점 은닉층의 셀에서 나온 결과값을 자신의 입력으로 사용한다.
  
---
### 예시 코드

MNIST 데이터를 RNN 모델을 적용한 것이다.\
RNN 모델 특성상 순서가 있는 데이터가 들어가야 하기 때문에 MNIST 이미지의 가로 한 줄(28픽셀)을 순서대로 28번 입력으로 넣어주는 모델로 만들 것이다.

1.15.0 버전 : https://colab.research.google.com/drive/17RZcKHAwVjyk9_MNt9y_BWU9nAhvd9T0

2.1.0-rc1 버전 : https://colab.research.google.com/drive/1OgbveGqpNHRTmKdlUXQ9mhXO7a97-lK0

---
