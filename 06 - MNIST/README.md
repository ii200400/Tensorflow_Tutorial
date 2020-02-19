# MNIST

MNIST란, 손으로 쓴 숫자들의 이미지를 모아놓은 데이터셋이다.\
다른 언어에서 첫 프로그램을 만들 때\
'Hello World!'를 출력하는 것처럼\
머신러닝을 공부하는 사람들이\
이미지들을 1~9로 분류하는 첫 모델을 만드는데 사용한다.

MNIST를 포함한 이후의 모델들은 텐서플로우에서 제공하는 함수로 구현할 것이다.\
책은 해당 함수가 구현되기 전에 만들어졌는지 전혀 소개가 되어있지 않다.

때문에 코드가 많이 달라지는데 훨씬 더 간편하고 직관적이라서\
앞으로 설명은 책의 도움을 받지만 코드 구현은 2.x버전에 더 비중을 둘 것이다.

## MNIST 학습해보기

> 모델 학습에 대한 용어

+ 학습 데이터(train data) : 모델이 학습할 때 사용하는 데이터이다.
+ 테스트 데이터(test data) : 모델이 학습이 잘 되었는지 확인하는 데이터이다. 학습 데이터와 테스트 데이터는 일반적으로 구분해서 사용한다.
+ 반복(iteration) : 모델의 가중치를 한 번 업데이트하는 작업
+ 배치(batch) : 모델 학습이 1회 iteration할 때 사용되는 데이터 셋의 여러 행(데이터와 라벨에 관한 정보)
  + 배치 크기(batch size) : 모델 학습이 1회 iteration할할 때 사용될 데이터 셋의 행의 수, 배치의 크기
  + 미니 배치(mini-batch) : 전체 배치 중에서 무작위로 선택한 배치의 부분집합
    + 한번에 학습에 사용되는 배치의 데이터 양이 컴퓨터 메모리를 넘기면 안되므로 사용하는 기법이다.
+ 에폭/에포크(epoch) : 전체 데이터 세트의 각 데이터들을 한번씩 학습하는 것을 의미한다.
  + 전체 데이터 셋이 1000개이고 batch가 100이라면 한 에폭은 1000/100번의 iteration으로 수행된다고 할 수 있다.

> 모델의 레이어에 관한 용어

+ Flatten : 2차원 데이터를 길게 늘려서 1차원의 데이터로 만드는 것을 의미한다.
  + [[1,2],[3,4]] --> [1,2,3,4]
+ 밀집 레이어(dense layer) : 각 노드가 뒤의 히든 레이어의 모든 노드에 연결된 히든 레이어이다.
  + 밀집 레이어(dense layer)를 완전 연결 레이어(fully connected layer)라고도 한다.
+ 과대적합(overfitting) : 모델이 훈련 데이터는 잘 예상을 하지만 그 외의 데이터는 예상이 잘 되지 않는 것을 의미한다.
+ 과소적합(underfitting) : 모델이 아직 훈련이 덜 되어 훈련 데이터와 테스트 데이터 모두 예상을 잘 못하는 것을 의미한다.
  + 과대적합과 과소적합에 관한 동영상(동영상의 variance는 weight를 의미한다고 생각하고 보자.)\
  https://www.youtube.com/watch?v=SjQyLhQIXSM&list=PLkDaE6sCZn6Hn0vK8co82zjQtt3T2Nkqc&index=2

> 모델의 레이블에 대한 용어

+ 희소 벡터(sparse vector) : 대부분의 값이 0이거나 비어있는 벡터(숫자들의 배열, 흔히 1차원 배열로 생각하는 것)
+ 원-핫 인코딩(one-hot encoding) : 요소중 하나가 1이고 나머지가 모두 0인 특징을 가지는 희소벡터
+ 정수 인코딩(integer encoding) : 정수만으로 표현되어지는 인코딩 방식 
  + 원-핫 인코딩이 다음과 같다면 [[0,1,0],[0,0,1],[1,0,0],[0,1,0],[0,1,0]]\
  위의 데이터를 정수 인코딩으로 바꾸면 다음과 같다. [2,3,1,2,2]

---
### 예시 코드

1.15.0 버전 : https://colab.research.google.com/drive/12X33MLRhL80_2eD1UdV_NQQPqUTuIFXg

2.1.0-rc1 버전 : https://colab.research.google.com/drive/1msKfEvtz2Has0EbLs0PvreGmCEzcAB9L

---

## 과대적합과 Dropout

+ 정규화(regularization) : 모델을 간단하게 만들어 과적합을 방지하는 기법
  + 종류로는 L1 정규화(L1 regularization), L2 정규화(L2 regularization), 드롭아웃(dropout), 조기 중단(early stopping) 등이 있다.
  + 실재로 epoch를 30으로 지정하고 위의 모델과 아래 모델를 비교하면 위의 코드의 모델은 과적합이 일어나 성능이 좋지 못한 것을 발견할 수 있다.(MNIST에서는 차이가 크게 와닿지 않지만 학습데이터가 적을수록, epoch를 더 크게 할 수록 심히지는 것을 볼 수 있다.)
+ 드롭아웃(dropout) : 정규화 방법중 하나로 특정 레이어의 뉴런을 무작위로 선택하고 일시적으로 신경망에서 삭제한다.
+ 배치 정규화(batch normalization) : regularization으로 분류되지는 않지만 과적합을 막아주고 출력값을 안정시키고 학습 속도도 향상시켜주는 기법
  + regularization과 normalization 모두 정식 구글 번역에서 정규화라고 쓰고있다;;

+ matplotlib : 그래프를 편하게 그릴 수 있도록 한 파이썬 라이브러리이다. \
간단한 그림이나 그래프들을 즉석으로 확인하고 싶을 때 자주 사용한다.

---
### 예시 코드

1.15.0 버전 : https://colab.research.google.com/drive/1gtBYEoIbg03OdENyUfiQ-Omji3kjmyuL

2.1.0-rc1 버전 : https://colab.research.google.com/drive/1s2FkyGPWksp7gmjdSbTJdeQCySPht5C5

---
