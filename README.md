# Today_Feeling
실시간 AI 감정 인식을 활용한 맞춤형 음악 추천 서비스

## Introduction

본 프로젝트는 사람의 얼굴 영상에서 감정을 인식하여 노래를 추천해주는 서비스를 제공한다. 사용자는 어플리케이션만 켜 놓으면 자동으로 기분에 맞는 맞춤형 노래를 추천 받을 수 있다.

## ✨ Demo

### emotion recognition
<p align ="center">
  <img src = "https://user-images.githubusercontent.com/90328527/224226104-af4303c1-e0cc-4080-ad85-6b83f278244a.gif">
</p>

### music recommend
<p align ="center">
  <img src = "https://user-images.githubusercontent.com/90328527/224226181-d7a7eaea-f0d0-43fb-82b6-2be2779d787e.gif">
</p>

## Dataset
|Data|데이터 수|Train 데이터 수|Val 데이터 수|세부사항|
|:-:|:-:|:-:|:-:|:-:|
|1|7853|7199|654|anger|
|2|6952|6275|677|fear|
|3|7624|6967|657|happiness|
|4|7191|6540|651|neutral|
|5|7499|6833|666|sadness|
|6|6988|6354|634|surprise|

학습에는 aihub의 한국인 감정 인식데이터 데이터 셋을 활용, 카테고리 별로 약 7000개로 구성된다.

출처 : https://aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=realm&dataSetSn=82

## Model
![model](https://github.com/SangBeom-Hahn/Today_Feeling/blob/main/assests/model.PNG)

전체적인 파이프라인은 Face Detection과 Emotion Recognition으로 진행된다. 얼굴 탐지에서 전체 이미지에서 얼굴만 crop한다. 카메라 앵글로 얼굴만 입력되는 것이 아니기 떄문에 영상이 프레임 단위로 들어가면 얼굴만 추출해야한다. 

얼굴을 탐지하였으면 감정 인식을 진행한다. 모델은 얼굴에서 34개의 Landmark를 추출하여 감정 인식의 정확도를 높힌다. 결과적으로 모델에 영상을 넣으면 감정을 인덱스로 추출한다.

※ 감정 리스트 : {anger, fear, happiness, sadness, surprise, neutral}

## Project Structure
![Structure](https://github.com/SangBeom-Hahn/Today_Feeling/blob/main/assests/struct.png)

```
Today_Feeling
├── Android
├── DB
├── Flask_server
├── Test
├── Web
├── models
├── docker-compose-main.yaml
└── docker-compose.yaml
```

- Android : 안드로이드 root 프로젝트 폴더(: 최종 release.zip)
- DB : AWS DB 접속 폴더
- Flask_server : 서버 구현 폴더
- Test : 테스트 서버 배포 폴더
- Web : 웹페이지 템플릿 폴더
- models : 모델 폴더
- docker-compose-main.yaml : 정식 서버 도커 컴포즈 파일
- docker-compose.yaml : 테스트 서버 도커 컴포즈 파일

## Getting started
- Download release.zip on Mobile Phone

## reference
- [Kaggle: FER Competition](https://www.kaggle.com/code/ashishpatel26/tutorial-facial-expression-classification-keras/notebook)
- [Face-alignment: How far are we from solving the 2D & 3D Face Alignment problem? (and a
dataset of 230,000 3D facial landmarks)
](https://arxiv.org/pdf/1703.07332.pdf)
- [facial-expression-recognition-using-cnn](https://github.com/amineHorseman/facial-expression-recognition-using-cnn)
- [Affect Expression Behaviour Analysis in the Wild using Spatio-Channel Attention and Complementary Context Information](https://paperswithcode.com/paper/affect-expression-behaviour-analysis-in-the)

## Feedback
- 속도가 느리더라도 완전 정확도에 초점을 맞춘 모델을 사용해도 될 것이다.
- 사용자 트래픽을 고려하여 모델을 프론트에 적재한 것이 인상 깊었다.
- few shot 러닝으로 지문 인식처럼 사용자마다 다른 감정을 정확하게 인식하는 방법이 있는데 이에 대해 고민해보면 좋을 것 같다.



## Author

👤 **SangBoem-Hahn**

- Github: [@SangBoem-Hahn](https://github.com/SangBeom-Hahn)
- Blog : [Tistory(Feeling_Manager)](https://hsb422.tistory.com/entry/%E3%85%81%EA%B0%90%EC%A0%95%EC%9D%B8%EC%8B%9D%EC%9D%84-%ED%99%9C%EC%9A%A9%ED%95%9C-%EC%8B%A4%EC%8B%9C%EA%B0%84-%EB%85%B8%EB%9E%98-%EC%B6%94%EC%B2%9C-%EC%84%9C%EB%B9%84%EC%8A%A4)
---
