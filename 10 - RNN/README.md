# 자연어 인식의 기본, RNN

한국어로 순환 신경망이라고 하는 RNN(Recurrent Neural Network)은 자연어나 음성과 같은 **순서**가 중요한 데이터를 처리하는데 강한 신경망이다.\
구글의 기계번역 또한 이 모델을 기반으로 만든 것이라고 한다.

이번 장에서는 음성, 자연어를 처리하는 RNN의 기본적인 사용법과 간단한 번역 프로그램을 만들 것이다.

## RNN 기본개념 익히기

참고 링크\
https://wikidocs.net/22886 \
https://rosypark.tistory.com/86 

+ 순환 신경망/RNN(Recurrent Neural Network) : 자연어나 음성과 같은 순서가 중요한 데이터(시계열 데이터)를 처리하는데 특화된 인공신경망
+ LSTM(Long Short-Term Memory) : 장기 기억력을 가지지 못하는 RNN을 보완하기 위해서 나온 신경망
+ GRU(Gated Recurrent Units) : LSTM과 비슷하지만 구조를 더 간소화한 신경망
+ 셀(cell) : 은닉층에서 활성화 함수를 통해 결과를 내보내는 역할한다. 
  + 이전의 값을 기억하려고 하는 일종의 메모리 역할을 수행하기 때문에 메모리 셀 혹은 RNN 셀이라고 한다.
  + 이전 시점 은닉층의 셀에서 나온 결과값을 자신의 입력으로 사용한다.
  
---
### 예시 코드

MNIST 데이터를 RNN 모델을 적용한 것이다.\
RNN 모델 특성상 순서가 있는 데이터가 들어가야 하기 때문에 MNIST 이미지의 가로 한 줄(28픽셀)을 순서대로 28번 입력으로 넣어주는 모델로 만들 것이다.

실재로 RNN이 이러한 방식으로 사용되지는 않지만 개념을 익히면서 할 수 있는 간단한 코드로 시작하기 위해서 만들었다.

1.15.0 버전 : [01_MNIST.ipynb](https://github.com/ii200400/Tensorflow_Tutorial/blob/master/10%20-%20RNN/01_MNIST.ipynb)

2.1.0-rc1 버전 : [01_MNIST(2_1ver).ipynb](https://github.com/ii200400/Tensorflow_Tutorial/blob/master/10%20-%20RNN/01_MNIST(2_1ver).ipynb)

---

## 단어 자동 완성

영문자 4개로 구성된 단어를 학습시켜 3글자만 주어졌을 때 자동으로 남은 한 글자를 추천하여 단어를 완성시킬 수 있는 신경망을 만들어보겠다.

실재로는 다양한 길이의 단어를 자동완성해주는 것이 일반적이지만 코드가 복잡해지는 관계로 문자길이를 고정하고 만들었다.\
학습시킬 데이터는 영문자로 구성된 임의의 영단어이고, 한 문자가 하나의 단계의 입력값이 될 것이다.

---
### 예시 코드

1.15.0 버전 : [02_Autocomplete.ipynb](https://github.com/ii200400/Tensorflow_Tutorial/blob/master/10%20-%20RNN/02_Autocomplete.ipynb)

2.1.0-rc1 버전 : [02_Autocomplete(2_1ver).ipynb](https://github.com/ii200400/Tensorflow_Tutorial/blob/master/10%20-%20RNN/02_Autocomplete(2_1ver).ipynb)

---
