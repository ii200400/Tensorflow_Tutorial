# 자동 생성기 GAN

GAN(generative Adversarial network)은 오토인코더와 같이 입력한 데이터와 같은 크기를 가지는 출력 데이터를 생성하는 모델 중 하나이다.\
서로 대립하는 두 신경망을 경쟁시키면서 모델을 학습시키는 것이 특징이다.

GAN을 제안한 이안 굿펠로우(Ian Goodfellow)가 논문에서 제시한 비유를 인용하면 다음과 같다.

위조지폐범(생성자)와 결찰(감식자)가 있다.\
범인은 경찰을 최대한 속이려고 더욱 더 식별하기 어려운 위조지폐를 만들고\
경찰은 위조한 지폐를 감별하려고 노력을 하는 것이다.

위조지폐범과 경찰이 경쟁을 하면서 서로의 능력이 발전하여\
결국 위조지폐범은 진짜와 다를 점이 없는 위조지폐를 만들 수 있게 된다는 것이 GAN 모델의 학습 방법이다.


## GAN 기본 용어

+ 생성자(generator) : 생성자는 실제 데이터로 학습하고 이를 바탕으로 거짓 데이터를 생성한다.
+ 감식자/구분자(discriminator) : 데이터가 진짜인지 생성자가 내놓은 가짜인지 판별하도록 학습한다.
+ 노이즈(noise) : 생성자에게 주는 무작위 입력값을 의미한다.

+ GAN의 특징
  1. 서로 경쟁을 할 두 모델(생성자, 감식자)을 만든다.
  2. GAN의 목표는 두 모델의 손실값을 최대화 하는 것이다.
  3. 생성자 모델은 스스로가 만든 가짜 이미지를 감식자 모델이 구별을 못 했을 때 손실값이 증가한다.\
  즉, 생성자 모델은 감식자 모델을 속이는 가짜 이미지를 만드는 것이 목표이다.
  3. 감식자 모델은 실재 이미지와 가짜 이미지를 잘 구별할 수록 손실값이 증가한다.
  4. 생성자는 가짜 이미지로 감식자를 속이면 손실값이 올라가고 감식자는 가짜 이미지를 잘 구별하면 손실값이 오르기 때문에 **두 모델의 손실값은 최대화를 목포로하지만 무한정 올라가진 않는다.**
  + 참고 링크\
  https://www.samsungsds.com/global/ko/support/insights/Generative-adversarial-network-AI-2.html

---
### 예시 코드

1.15.0 버전 : [01_GAN.ipynb](https://github.com/ii200400/Tensorflow_Tutorial/blob/master/09%20-%20GAN/01_GAN.ipynb)

2.1.0-rc1 버전 : [01_GAN(2_1ver).ipynb](https://github.com/ii200400/Tensorflow_Tutorial/blob/master/09%20-%20GAN/01_GAN(2_1ver).ipynb)

2.1버전에서 사용자 정의 손실 함수를 사용하게 되는데 실수를 해서 에러 찾는데만 시간이 좀 오래걸렸다;
텐서플로우 공식 사이트의 튜토리얼을 참고하면서 책에서 구현된 모델을 적용하였다. 

---

## GAN 두번째 실습

위와 비슷한 코드이지만 라벨을 활용하여 원하는 숫자가 출력될 수 있도록하는 코드를 만들어보겠다.

---
### 예시 코드

1.15.0 버전 : [02_GAN2.ipynb](https://github.com/ii200400/Tensorflow_Tutorial/blob/master/09%20-%20GAN/02_GAN2.ipynb)

2.1.0-rc1 버전 : [02_GAN2(2_1ver).ipynb](https://github.com/ii200400/Tensorflow_Tutorial/blob/master/09%20-%20GAN/02_GAN2(2_1ver).ipynb)

2.1버전은 학습률을 재대로 설정해주지 않으면 잘 학습이 되지 않는 점을 확인하였다.
덕분에 내 4일이 승화하였다.

---

솔직히 사용자 지정 손실 함수와 최적화 설정을 사용하여서 코딩을 이해하는데 조금 어려웠다.\
나중에 한 번 더 보고 이해를 해야할 것 같다.

GAN 논문 한글 리뷰 링크\
http://jaejunyoo.blogspot.com/2017/01/generative-adversarial-nets-1.html

