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
    + 스트라이드(stride) : 슬라이스를 얼마나 움직일지 결정한다.
    + 패딩(padding) : 입력변수 주변에 0이나 특정한 값으로 두르는 것을 의미한다.
      + https://hyunyoung2.github.io/2018/07/23/Tensorflow%27s_Neural_Network_Convolution/ 
  + 컨볼루셔널 필터(convolutional filter) : 슬라이스의 크기와 같은 크기를 가지며 크기에 맞는 가중치와 1개의 편향을 가지고 있다.\
    + 만약 3\*3 슬라이스가 있다면 그것의 필터는 [3,3] 크기이고 3\*3개의 가중치와 1개의 편향을 가진다.
    + 컨볼루셔널 커널(kernel)이라고도 부른다.
  + 풀링(pooling) : 컨볼루셔널 레이어에서 생성된 행렬을 작은 행렬로 줄이는 과정이다.

+ 완전 연결 레이어(fully connected layer) : 인접한 레이어의 모든 뉴런과 연결된 레이어를 의미한다.

---
### 예시 코드

1.15.0 버전 : https://colab.research.google.com/drive/1Py8danNdcFQjL09Z3L7RXu2IA1F_n2ma

2.1.0-rc1 버전 : https://colab.research.google.com/drive/1IpJoglfVaezXX580mheLFbSn_kf5FdSD

---
