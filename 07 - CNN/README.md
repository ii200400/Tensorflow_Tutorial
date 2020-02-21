# 이미지 인식의 대표적 신경망, CNN

CNN(convolutional neural network)는 합성곱 신경망이라고 부른다.\
1998년에 얀 레쿤(Yann LeCun)이라는 교수가 소개하였으므로 나보다 2살 어리지만 매우 유명한 알고리즘이다.

특히 이미지 인식 분야에서 뛰어난 두각을 보인다고 하는 이 CNN에 관해 약간의 이론을 공부하고 실습을 해볼 것이다.

## CNN 기본 개념

같은 의미인데 부르는 방법이 여러가지인지 시간이 지나면서 부르는 명칭이 바뀐 것인지는 모르겠으나\
확실하게 같은 의미인데 명칭이 2가지인 경우가 몇 개 있다.\
구글 용어집을 기준으로 쓰되 이전 용어도 같이 작성하고 넘어가겠다.

+ 컨볼루셔널 레이어(convolutional layer)
  + 스트라이드(stride)
  + 컨볼루셔널 필터(convolutional filter)
    + 커널(kernel)
  + 슬라이스 (slice)
    + 윈도우(window)
+ 풀링(pooling)
+ 완전 연결 레이어(fully connected layer)

---
### 예시 코드

1.15.0 버전 : https://colab.research.google.com/drive/1Py8danNdcFQjL09Z3L7RXu2IA1F_n2ma

2.1.0-rc1 버전 : https://colab.research.google.com/drive/1IpJoglfVaezXX580mheLFbSn_kf5FdSD

---
