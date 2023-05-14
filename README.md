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

## Features
1. 로그인
    - consolelog 기능
2. 회원가입
3. 노래 관련
    - 관심 노래 목록 선택 및 변경
    - 노래 추천 및 중지
4. 기분 관련
    - 현재 기분 선택
    - 기분 통계 확인

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
- 사용자마다 핸드폰과 웹 캠 거치하는 위치가 다르니 앱 시작 시 메뉴얼을 제공했으면 좋겠다.
- 서버단에서 사용자 트래픽을 고려하여 모델을 프론트에 적재한 것이 인상 깊었다.



## Author

👤 **SangBoem-Hahn**

- Github: [@SangBoem-Hahn](https://github.com/SangBeom-Hahn)
- Blog : [Tistory(Feeling_Manager)](https://hsb422.tistory.com/entry/%EA%B0%90%EC%A0%95%EC%9D%B8%EC%8B%9D%EC%9D%84-%ED%99%9C%EC%9A%A9%ED%95%9C-%EC%8B%A4%EC%8B%9C%EA%B0%84-%EB%85%B8%EB%9E%98-%EC%B6%94%EC%B2%9C-%EC%84%9C%EB%B9%84%EC%8A%A4)
---
