# MNIST

MNIST란, 손으로 쓴 숫자들의 이미지를 모아놓은 데이터셋이다.\
머신러닝을 공부하는 사람들이\
마치 'Hello World!'를 출력하는 것처럼\
이미지들을 1~9로 분류하는 모델을 만드는데 사용한다.

MNIST를 포함한 이후의 모델들은 텐서플로우에서 제공하는 함수로 구현할 것이다.\
책은 해당 함수가 구현되기 전에 만들어졌는지 전혀 소개가 되어있지 않다.

때문에 코드가 많이 달라지는데 훨씬 더 간편하고 직관적이라서\
앞으로 설명은 책의 도움을 받지만 코드 구현은 2.x버전에 더 비중을 둘 것이다.

## MNIST 학습해보기

+ 배치(batch) : 모델 학습이 1회 반복할 때 사용되는 데이터 셋의 여러 행(데이터와 라벨에 관한 정보)
+ 배치 크기(batch size) : 배치 한번에 사용될 데이터 셋의 행의 수
+ 미니 배치(mini-batch) : 전체 배치 중에서 무작위로 선택한 소규모 배치 부분집합이다.
  + 배치에 쓰이는 데이터 양이 컴퓨터 메모리를 넘기면 안되므로 사용하는 기법이다.
  
+ Flatten
+ Dense

+ 원-핫 인코딩(one-hot encoding) : 
+ 정수 인코딩(integer encoding) : 

+ epochs
+ verbose

---
### 예시 코드

1.15.0 버전 : https://colab.research.google.com/drive/12X33MLRhL80_2eD1UdV_NQQPqUTuIFXg

2.1.0-rc1 버전 : https://colab.research.google.com/drive/1msKfEvtz2Has0EbLs0PvreGmCEzcAB9L

---
