# Today_Feeling
실시간 AI 감정 인식을 활용한 맞춤형 음악 추천 서비스

## Introduction

본 프로젝트는 사람의 얼굴 영상에서 감정을 인식하여 노래를 추천해주는 서비스를 제공한다. 사용자는 어플리케이션만 켜 놓으면 자동으로 기분에 맞는 맞춤형 노래를 추천 받을 수 있다.

## ✨ Demo


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
![model](https://github.com/SangBeom-Hahn/Sketch2Fashion/blob/main/assests/model.png)

전체적인 파이프라인은 Face Detection과 Emotion Recognition으로 진행된다. 얼굴 탐지에서 전체 이미지에서 얼굴만 crop한다. 카메라 앵글로 얼굴만 입력되는 것이 아니기 떄문에 영상이 프레임 단위로 들어가면 얼굴만 추출해야한다. 

얼굴을 탐지하였으면 감정 인식을 진행한다. 모델은 얼굴에서 34개의 Landmark를 추출하여 감정 인식의 정확도를 높힌다. 결과적으로 모델에 영상을 넣으면 감정을 인덱스로 추출한다.

※ 감정 리스트 : {anger, fear, happiness, sadness, surprise, neutral}

## Project Structure
![Structure](https://github.com/SangBeom-Hahn/Sketch2Fashion/blob/main/assests/model.png)

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

- Android : 안드로
- DB : 어플리케이션 루트 폴더
- Flask_server : 카테고리별 채색 모델 적재 폴더
- Test : 웹페이지 구성에 필요한 리소스를 모아놓은 폴더
- Web : 웹페이지 템플릿 폴더
- models : 라우팅 함수 구현 폴더
- docker-compose-main.yaml : 이미지 pair 구성 코드
- docker-compose.yaml : inference 코드
