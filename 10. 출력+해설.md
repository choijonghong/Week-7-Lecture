### 출력: CNN 인공지능 학습을 위한 CIFAR-10 데이터 준비 및 시각화
* <img width="1531" height="640" alt="image" src="https://github.com/user-attachments/assets/d88ec939-15dc-4ac3-80f2-4060ce58bf8d" />
* TensorFlow 2.19.0을 사용하여 CNN 인공지능 프로그램을 실행하였다.
* CIFAR-10 사진 60,000장을 불러와 학습용 50,000장과 테스트용 10,000장으로 구분하였다.
* 각 사진은 32×32픽셀의 컬러 이미지이며, 정답은 10개 종류로 구분된다.
* 학습용 사진 10장을 화면에 출력하고, 사진 아래에 고양이·자동차·개구리 등의 정답을 표시하였다.

### CNN 인공지능 모델의 신경망 구조
* <img width="979" height="490" alt="image" src="https://github.com/user-attachments/assets/0a07b48b-ccbe-4ad8-835f-4fd7c6552e64" />

* Conv2D(합성곱층)**는 32개 → 64개 → 128개의 필터를 사용하여 사진의 선, 모양 등 특징을 추출한다.
* MaxPooling2D(풀링층)**는 특징 맵의 크기를 32×32 → 16×16 → 8×8 → 4×4로 줄여 중요한 특징을 압축한다.
* Flatten(평탄화층)**은 4×4×128개의 특징을 2,048개의 숫자로 펼쳐 분류할 준비를 한다.
* Dense(완전연결층)**는 512개 → 256개의 뉴런으로 특징을 분석하고, Dropout은 과적합을 줄인다.
* 출력층(Dense 10)**은 사진을 10가지 종류로 분류하며, **Param #**은 각 층에서 학습할 가중치와 편향의 개수를 나타낸다.


### 학습 로그
<img width="979" height="490" alt="image" src="https://github.com/user-attachments/assets/68f9083a-fce2-4936-b646-090b85231eb3" />

* ﻿Total params: 1,276,234 (4.87 MB): 모델의 가중치는 약 128만 개입니다. 각 파라미터가 float32(4바이트)라서 약 4.87MB가 됩니다
* Trainable params: 학습 중에 업데이트되는 파라미터입니다. 전체가 학습 대상입니다.
* Non-trainable params: 0: 고정된 가중치가 없습니다. 사전학습 모델을 얼린(freeze) 부분이 없으니 처음부터 학습하는 모델입니다.
* <img width="783" height="324" alt="image" src="https://github.com/user-attachments/assets/46e5de68-f8e9-4887-b8cb-d1bceb457bac" />
* <img width="783" height="409" alt="image" src="https://github.com/user-attachments/assets/2bcdb2f0-ae73-4538-a672-c8f8c95877ef" />
* Model training finished.
* 313/313 - 2s - 6ms/step - accuracy: 0.7501 - loss: 1.0231


### 테스트 결과
* <img width="1059" height="515" alt="image" src="https://github.com/user-attachments/assets/a098e25a-cf88-4035-af98-b03fb9128128" />
* <img width="816" height="766" alt="image" src="https://github.com/user-attachments/assets/73b01e27-10e1-4370-bdf7-c55acb3ac934" />

  





