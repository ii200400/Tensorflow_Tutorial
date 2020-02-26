# 자동 생성기 GAN

GAN(generative Adversarial network)은 오토인코더와 같이 입력한 데이터와 같은 크기를 가지는 출력 데이터를 생성하는 모델 중 하나이다.\
서로 대립하는 두 신경망을 경쟁시키면서 모델을 학습시키는 것이 특징이다.

GAN을 제안한 이안 굿펠로우(Ian Goodfellow)가 논문에서 제시한 비유를 인용하면 다음과 같다.

위조지폐범(생성자)와 결찰(구분자)가 있다.\
범인은 경찰을 최대한 속이려고 더욱 더 식별하기 어려운 위조지폐를 만들고\
경찰은 위조한 지폐를 감별하려고 노력을 하는 것이다.

위조지폐범과 경찰이 경쟁을 하면서 서로의 능력이 발전하여\
결국 위조지폐범은 진짜와 다를 점이 없는 위조지폐를 만들 수 있게 된다는 것이 GAN 모델의 학습 방법이다.

## GAN 기본 용어

+ 생성자(generator) : 생성자는 실제 데이터로 학습하고 이를 바탕으로 거짓 데이터를 생성한다.
+ 감식자/구분자(discriminator) : 데이터가 진짜인지 생성자가 내놓은 가짜인지 판별하도록 학습한다.

---
### 예시 코드

1.15.0 버전 : https://colab.research.google.com/drive/17Q33wz8DWivousmXEtvtDHVwyjgT_ksT

2.1.0-rc1 버전 : https://colab.research.google.com/drive/1oCh4Er_UvY0tZFxGnrJ1QZnAnuWWnh8d

---
