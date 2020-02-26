# 비지도(Unsupervised) 학습 방법 대표, Autoencoder

머신러닝 학습 방법은 크게 지도 학습과 비지도 학습으로 나눌 수 있다.

비지도 학습 중 널리 쓰이는 방법으로 오토인코더(autoencoder)가 있는데 이것이 이번에 배울 내용의 주제이다.

## 오토 인코더 개념

+ 지도 학습(supervised learning) : 모델에게 입력값(x)과 그에 대응하는 실재값(y)을 알려주고 학습법
+ 비지도 학습(unsupervised learning) : 모델에게 입력값만 주고 실재값은 알려주지 않는 학습법

+ 오토인코더(autoencoder) : 입력값과 출력값이 같도록하는 신경망
  + 변이형 오토인코더(varialtional autoencoder), 잡음제거 오토인코더(denoising autoencoder) 등 많은 종류가 있다.
  + 은닉층의 노드(뉴런) 수가 입력값보다 적은 점과 입력 데이터를 압축하여 노이즈 제거에 매우 효과적인 것이 특징이다.
  
---
### 예시 코드

1.15.0 버전 : https://colab.research.google.com/drive/1oQ3d3Wsv5VOZ_ZV0ZoojIxL234-RhaEm

2.1.0-rc1 버전 : https://colab.research.google.com/drive/1Pw_YL3hZ0U5PDFgtoUGSW37g96Vf4w4p

---

오토인코더에 관한 링크\
https://keraskorea.github.io/posts/2018-10-23-keras_autoencoder/
