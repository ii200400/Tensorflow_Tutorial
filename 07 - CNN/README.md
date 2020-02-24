# 이미지 인식의 대표적 신경망, CNN

CNN(convolutional neural network)는 합성곱 신경망이라고 부른다.\
1998년에 얀 레쿤(Yann LeCun)이라는 교수가 소개하였으므로 나보다 2살 어리지만 매우 유명한 알고리즘이다.

특히 이미지 인식 분야에서 뛰어난 두각을 보인다고 하는 이 CNN에 관해 약간의 이론을 공부하고 실습을 해볼 것이다.

## CNN 기본 개념

같은 의미인데 부르는 방법이 여러가지인지 시간이 지나면서 부르는 명칭이 바뀐 것인지는 모르겠으나\
확실하게 같은 의미인데 명칭이 2가지인 경우가 몇 개 있다.\
구글 용어집과 CNN튜토리얼을 기준으로 쓰되 이전 용어도 같이 작성하고 넘어가겠다.

구글 CNN 튜토리얼 : https://developers.google.com/machine-learning/practica/image-classification/convolutional-neural-networks?hl=ko \
구글 용어집 : https://developers.google.com/machine-learning/glossary?hl=ko

+ 특성(feature) : 모델이 예측을 하기위한 입력변수를 의미한다.

+ 컨볼루셔널 신경망(convolutional neural network) : 적어도 하나의 레이어가 컨볼루셔널 레이어인 신경망이다.\
일반적으로 컨볼루셔널 신경망은 컨볼루셔널 레이어, 풀링 레이어, 밀집 레이어의 조합으로 구성된다.
+ 컨볼루셔널 레이어(convolutional layer) : 신경망의 한 레이어로 컨볼루셔널 필터를 통하여 연산을 하는 레이어를 의미한다.\
CNN 모델에서 자주 쓰이는 레이어 중 하나로 계산량이 줄어들고 메모리도 아끼면서 더 빠르게 학습시킬 수 있다는 특징이 있다.
  + 특징 맵/피처 맵(feature map) : 컨볼루셔널 레이어를 통해서 만들어진 출력값
  + 슬라이스 (slice) : 이미지나 특징 맵의 일부분으로 컨볼루셔널 필터와 함께 컨볼루셔널 연산을 수행할 때 사용된다.\
  윈도우(window)라고도 한다.
    + 스트라이드(stride) : 다음 슬라이스를 어떻게 만들지 결정한다.
    + 패딩(padding) : 입력변수 주변에 0이나 특정한 값을 임의로 넣어 출력 변수의 크기와 값을 조정한다.
      + 참고 링크(쿼라에서 padding='Same' 에 대한 글인데 사진과 함께 설명이 잘 되어있다.)\
      https://www.quora.com/What-does-the-same-padding-parameter-in-convolution-mean-in-TensorFlow
  + 컨볼루셔널 필터(convolutional filter) : 슬라이스의 크기와 같은 크기를 가지며 크기에 맞는 가중치와 1개의 편향을 가지고 있다.\
    + 만약 3\*3 슬라이스가 있다면 그것의 필터는 [3,3] 크기이고 3\*3개의 가중치와 1개의 편향을 가진다.
    + 컨볼루셔널 커널(kernel)이라고도 부른다.
  + 풀링(pooling) : 컨볼루셔널 레이어에서 생성된 행렬을 작은 행렬로 줄이는 과정이다.

+ 완전 연결 레이어(fully connected layer) : 인접한 레이어의 모든 뉴런과 연결된 레이어를 의미한다.

CNN 네트워크를 이해하기 위해 참고한 사이트\
http://taewan.kim/post/cnn/

---
### 예시 코드

1.15.0 버전 : https://colab.research.google.com/drive/1Py8danNdcFQjL09Z3L7RXu2IA1F_n2ma

2.1.0-rc1 버전 : https://colab.research.google.com/drive/1IpJoglfVaezXX580mheLFbSn_kf5FdSD

---

## 고수준 API

신경망 구성을 손쉽게 해 주는 유틸리티 모음인 tensorflow.layers 를 활용하여 모델을 만들어본다.

위의 코드와 크게 다른점은 없고 말 그대로 고수준API를 사용하는 방법을 보여준다.\
2.1버전은 작성하지 않았다. 이미 활용하고 있었기 때문이다.\
tf.summary() 등등으로 레이어의 구조를 글과 그림으로 볼 수 있고 코딩 속도와 학습 속도도 더 빠르다.\
굳이 쓰지 않을 이유가 없고 더 자세히 알고 싶으면 이론을 공부하는 편이 더 좋다고 생각한다;;

하지만 글쓴이는 기본을 더 중요하게 생각하고 고수준 API를 사용하지 않고 코딩하는 것이 더 기본을 닦는 것에 도움이 된다고 생각하여 \
책에서는 고수준API 쓰는 것을 지양하였다.

---
### 예시 코드

1.15.0 버전 : https://colab.research.google.com/drive/1xNMBVnPRB2Xnd2HwKYmXFGpI-Y2W5r4l

아니;; 고수준 API로만 바꾸고 레이어는 완전히 같은 줄 알았는데\
padding도 안쓰고 use_bias=False로도 안하고 rate = 1 - keep_prop여서 0.3을 넣어야하는데 0.7을 넣는 등, \ 
틀린 점이 너무 많다;;;

오래전에 쓰여진 글이니까 2년이 지나면서 함수가 바뀐 것인지 글쓴이가 잘못한 것인지 알수가 없지만\
그래도 코드를 만들어 놓긴 하였으니 코드를 올리겠다. 참고만 하자.

---
