# 텐서플로우를 공부하기 위해 만든 저장소!

1. 해당 내용들은 모두 '골빈해커의 3분 딥러닝 텐서플로맛'이라는 책을 참고로 만든 저장소이다.
2. 책에서 등장한 코드는 https://github.com/golbin/TensorFlow-Tutorials 에서 찾아볼 수 있다.   
   하지만, 책에는 없으나 스스로 궁금했던 부분까지 추가하여 작성할 수도 있다.
3. 이 저장소에는 스스로 알아보거나 이해했던 내용을 적어넣을 것이다. 즉, 주석이 아주.. 주관적이다.
4. 책에 쓰여진 코드와 이를 위한 기본 내용을 중점으로 기술할 것이다.
5. 노트북이 느린 관계로 '골빈해커'와는 다르게 google colab 환경에서 코드를 실행할 것이다.
6. 책이.. 2년도 더 전에 쓰여져 현재의 2.x버전의 텐서플로와 **맞지 않는 문법**과 설명이 꽤 있기 때문에 스스로 공부하면서 참고한 내용을 많이 추가할 것이다.
    + 위의 사항 때문에 오히려 이 책을 비추천하는데 책을 이미 사기도 하였고 내용을 한번 훑어보는 겸 보고있다.   
      구버전 문법을 배우는 격이니 만약 비전공자라면 책을 사지 말것을 강력하게 권고한다.
7. 해당 저장소에서 볼 수 있는 ipynb코드는 필자의 구글 드라이브에도 똑같이 있다. 
    + [구글 드라이브 공유 링크](https://drive.google.com/drive/folders/1CvTsZd4tNENO6k4czETr83W6NcHF1gp6?usp=sharing)

**현재 필자는 AI 기본 개념만 해당 저장소에 정리하고 안드로이드로 전향한 상태이므로 더 이상의 업데이트는 없을 예정이다.**

# 목차

1. [딥러닝 기본 개념과 텐서플로](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/01%20-%20Why%20TensorFlow)
2. [설치와 에러](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/02%20-%20Preparation)
    + [Jupyter Notebook과 Google Colab](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/02%20-%20Preparation#jupyter-notebook%EA%B3%BC-google-colab)
3. [텐서플로 프로그래밍을 위한 기본기](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/03%20-%20TensorFlow%20Basic)
    + [텐서플로의 자료형과 작동방식](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/03%20-%20TensorFlow%20Basic#%ED%85%90%EC%84%9C%ED%94%8C%EB%A1%9C%EC%9D%98-%EC%9E%90%EB%A3%8C%ED%98%95%EA%B3%BC-%EC%9E%91%EB%8F%99%EB%B0%A9%EC%8B%9D)
    + [선형 회귀 모델을 통한 실습](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/03%20-%20TensorFlow%20Basic#%EC%84%A0%ED%98%95-%ED%9A%8C%EA%B7%80-%EB%AA%A8%EB%8D%B8%EC%9D%84-%ED%86%B5%ED%95%9C-%EC%8B%A4%EC%8A%B5)
4. [신경망 구현](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/04%20-%20Neural%20Network%20Basic)
    + [딥러닝 기본 개념](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/04%20-%20Neural%20Network%20Basic#%EB%94%A5%EB%9F%AC%EB%8B%9D-%EA%B8%B0%EB%B3%B8-%EA%B0%9C%EB%85%90)
    + [역전파](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/04%20-%20Neural%20Network%20Basic#%EC%97%AD%EC%A0%84%ED%8C%8C)
    + [분류 모델 실습 (단일 신경망)](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/04%20-%20Neural%20Network%20Basic#%EB%B6%84%EB%A5%98-%EB%AA%A8%EB%8D%B8-%EC%8B%A4%EC%8A%B5-%EB%8B%A8%EC%9D%BC-%EC%8B%A0%EA%B2%BD%EB%A7%9D)
    + [분류 모델 실습 (다중 신경망)](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/04%20-%20Neural%20Network%20Basic#%EB%B6%84%EB%A5%98-%EB%AA%A8%EB%8D%B8-%EC%8B%A4%EC%8A%B5-%EB%8B%A4%EC%A4%91-%EC%8B%A0%EA%B2%BD%EB%A7%9D)
5. [텐서보드와 모델 재사용](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/05%20-%20TensorBoard%2C%20Saver)
    + [모델을 저장하고 불러오기](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/05%20-%20TensorBoard%2C%20Saver#%EB%AA%A8%EB%8D%B8%EC%9D%84-%EC%A0%80%EC%9E%A5%ED%95%98%EA%B3%A0-%EB%B6%88%EB%9F%AC%EC%98%A4%EA%B8%B0)
    + [텐서보드 사용하기](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/05%20-%20TensorBoard%2C%20Saver#%ED%85%90%EC%84%9C%EB%B3%B4%EB%93%9C-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0)
6. [MNIST](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/06%20-%20MNIST)
    + [MNIST 학습해보기](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/06%20-%20MNIST#mnist-%ED%95%99%EC%8A%B5%ED%95%B4%EB%B3%B4%EA%B8%B0)
    + [과대적합과 정규화](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/06%20-%20MNIST#%EA%B3%BC%EB%8C%80%EC%A0%81%ED%95%A9%EA%B3%BC-%EC%A0%95%EA%B7%9C%ED%99%94)
7. [이미지 인식의 대표적 신경망, CNN](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/07%20-%20CNN)
    + [CNN 기본 개념](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/07%20-%20CNN#cnn-%EA%B8%B0%EB%B3%B8-%EA%B0%9C%EB%85%90)
    + [고수준 API](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/07%20-%20CNN#%EA%B3%A0%EC%88%98%EC%A4%80-api)
8. [비지도(Unsupervised) 학습 방법 대표, Autoencoder](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/08%20-%20Autoencoder)
    + [오토 인코더 개념](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/08%20-%20Autoencoder#%EC%98%A4%ED%86%A0-%EC%9D%B8%EC%BD%94%EB%8D%94-%EA%B0%9C%EB%85%90)
9. [자동 생성기 GAN](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/09%20-%20GAN)
    + [GAN 기본 용어](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/09%20-%20GAN#gan-%EA%B8%B0%EB%B3%B8-%EC%9A%A9%EC%96%B4)
    + [GAN 두번째 실습](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/09%20-%20GAN#gan-%EB%91%90%EB%B2%88%EC%A7%B8-%EC%8B%A4%EC%8A%B5)
10. [자연어 인식의 기본, RNN](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/10%20-%20RNN)
    + [RNN 기본개념 익히기](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/10%20-%20RNN#rnn-%EA%B8%B0%EB%B3%B8%EA%B0%9C%EB%85%90-%EC%9D%B5%ED%9E%88%EA%B8%B0)
    + [단어 자동 완성](https://github.com/ii200400/Tensorflow_Tutorial/tree/master/10%20-%20RNN#%EB%8B%A8%EC%96%B4-%EC%9E%90%EB%8F%99-%EC%99%84%EC%84%B1)
11. [Inception]() 
    + 미구현
13. [DQN]() 
    + 미구현
