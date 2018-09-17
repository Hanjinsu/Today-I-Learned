# Deep Learning

## Deep Learning 모델의 손실함수

딥러닝 모델의 손실함수로 음의 로그우도(negative log-likelihood)가 자주 쓰인다.

- 확률론적 접근 : P(Y|X;W)를 최대화하는 W가 찾고 싶은 결과이다. 그러나 학습데이터 각각의 우도를 스케일해도 전체 arqmax의 결과는 바뀌지 않으므로 로그우도의 기대값, 즉 log를 씌운것을 최대로 하는 W와 동일하다. 따라서 sortmax 함수를 취하여 요소의 합이 1이 되게 하고 정답 인덱스에 해당하는 f요소값을 높이면서 최대우도추정을 수행하는 것이다.

- 정보이론적 접근 : 두 확률분포 p와 q 사잉의 차이를 계산하는 데에 cross entropy 라는 함수가 적용된다. 가진 데이터의 분포와 예측한 결과사이의 분포사이의 차이인 cross entrophy를 최소화 하는 것이 중요하다.

- negative log-likehood의 장점 : 음의 로그우도로 손실을 정의하면 cross entrophy가 되며, 모델에 다양한 확률분포를 가정할 수 있게 된다. 또한 딥러닝 역전파시 gradient가 죽는 문제를 해결가능 하며, gradient를 비교적 쉽게 구할 수 있다.

## 하이퍼 파라미터

- 머신러닝 알고리즘에는 지정해야 할 세팅들이 있는데 이런 튜닝옵션을 *하이퍼파라미터*라고 부르며 성능을 최적화 하거나 편향과 분산 사이의 균형을 맞출 때 알고리즘을 조절하기 위해 사용된다. 
- 하이퍼 파라미터의 종류 : Hidden Layer의 수, Node의 수, 학습률 등이 포함된다. 넓게 보면, testset과 trainset도 해당된다.

## Hidden Layer

- 역할 : 딥러닝은 단어에서도 나와 있듯이 깊은 학습을 위해서는 input과 output사이에 hidden layer가 필요하다. Hidden Layer의 개수는 보통 큰 input을 갖고 작은 output을 원할 때 점점 줄여주는 방식으로 구현된다.  

- Hidden Layer와 역전파 : 학습은 오류역전파로 가중치들을 조정하면서 최적의 결과를 찾는다. 끝 Hidden Layer부터 차근차근 앞으로 역전파를 해나가는 방식이다. 그러나 Hidden Layer의 개수가 많은 경우에 sigmoid함수를 쓴다면 점점 앞으로 올 수록 손실값이 줄어드는 vanishing gradient문제가 발생한다. 2006년 Hiton 교수가 sigmoid함수 대신 ReLU 함수를 제안하여 이 문제를 해결했다.

![Sigmoid 함수](https://taewanmerepo.github.io/2017/09/sigmoid/post.jpg)
![ReLU 함수](https://t1.daumcdn.net/cfile/tistory/26261B4957F21DB42C)

- Hidden Layer 생성방법 : 초기 가중치값을 랜덤으로 배정하는 것은 학습 효율적으로 위험할 확률이 크다. 각 Hidden Layer사이의 가중치들을 전부 랜덤으로 배정하는 것은 더 큰 혼란을 불러올 수 있다. 따라서 Hidden Layer 하나를 학습시키고 weigth를 집어넣게 되는데 이때 input과 output을 동일하게 하여 자기 자신을 인식할 수 있도록 초기 weight값을 잡아준다.

## CNN

- CNN은 Convolutional Neaural Network로 convolution이 중요시 되는 학습법이다.

- 이미지 인식에서 예를 들자면 
!

