# hand-sign-recognition 

## 프로그램 개요
  카메라를 통해 실시간으로 손동작을 입력 받으면 수화 의미를 분류하는 프로그램.
  직접 학습시킨 모델을 이용해서 실시간 이미지 데이터를 분류.
  정지된 이미지의 수화가 아닌 동작을 의미하는 수화들을 분류할 수 있다는 점에서 작품성이 있다.

![그림3](https://user-images.githubusercontent.com/84042702/164878809-c26707f2-b2ac-4c21-aaf0-b4d574a8a5d8.png)

![그림4](https://user-images.githubusercontent.com/84042702/164878873-0b36f23d-6f0d-4a22-97f4-0995edb8ce20.png)


## 프로그램 환경
  개발도구 – Python3.7.3, Jupyter notebook
  Package  - tensorflow, keras, mediapipe, LSTM, openCV …

## 프로그램 흐름도
  1. 카메라를 이용해서 실시간으로 영상을 입력 받는다.
  2.  얼굴, 포즈, 손을 인식해서 keypoint를 구한다. Keypoint는 x,y,z위치 정보를 가진다.
  3.  keypoint를 이용해서 동작을 예측한다.



