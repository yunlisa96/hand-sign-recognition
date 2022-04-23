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

## 학습데이터
  - 수화를 의미하는 학습데이터를 직접 생성<br/>
  - 학습데이터는 left-hand, right-hand, pose의 keypoint들로 이루어져있다.<br/>
  - 30 frame을 1 sequence로 설정 <br/>
  - 수화 하나당 약 200개의 sequence data를 생성 <br/>
  - 총 78,000개의 학습데이터 생성(200x13x30)<br/>
![학습](https://user-images.githubusercontent.com/84042702/164879642-03bed53b-029c-4923-b179-49b7afa14f89.PNG)

## 신경망 설계 
 - LSTM 구조 신경망
 - 긴 시퀀스의 입력을 처리하는데 좋음
 - 입력층의 크기 258*학습데이터 수, 출력층의 크기 13개
 
## 신경망 모델 성능 평가
![성능평가](https://user-images.githubusercontent.com/84042702/164880896-69116ec2-c639-4fad-9190-5d551796b6ae.PNG)
| gesture  | accuracy | gesture   | accuracy |
|----------|----------|-----------|----------|
| yes      | 99%      | do it     | 100%     |
| no       | 99%      | glad      | 99%      |
| hate     | 97%      | good      | 98%      |
| don't    | 99%      | bad       | 99%      |
| fine     | 99%      | tired     | 100%     |
| sorry    | 100%     | follow me | 100%     |
| let's go | 99%      |           |          |
 
## 프로그램 UI
  - 분류된 수화 의미를 화면 상단에 텍스트로 출력 
  - 이전에 분류했던 수화 의미를 5개까지 출력해주면 왼쪽에서 오른쪽 순서대로 업데이트하여 출력
  - 분류할 때 가장 높은 확률을 가진 두개의 수화 의미와 확률을 왼쪽 상단에 출력
![image](https://user-images.githubusercontent.com/84042702/164882419-88cbd896-f8a2-49f8-bc44-4442abfc9817.png)
