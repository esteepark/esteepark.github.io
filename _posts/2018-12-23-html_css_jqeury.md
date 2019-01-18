---
layout: post
title: "html, css, jquery"
excerpt: ""
categories: [front-end]
date: 2018-12-23 22:00:00
comments: true
---

- client = 고객 = 의뢰인 = 웹을 사용하는 사람
- host = 주인 = 진행자 = 웹을 통해 서비스하는 콘텐츠 제공자

- world wide web = 온라인에서 이루어지는 거래 
- 오프라인에서의 거래 = 물건을 주고받는 것
- 온라인에서의 거래 = 정보data를 주고받는 것

------------------> 요청(Request)
client     os     web browser     host
<----------------- 응답(Response)

- OS = 운영체제 = Operating System = 사용자가 컴퓨터를 쉽게 사용할 수 있도록 인터페이스를 제공해주는 프로그램들의 집합
- Web Browser = OS에 설치되는 여러 프로그램 중 하나로 사용자를 웹 세상으로 안내하는 역할
- 대표적인 웹 브라우저 = 인터넷 익스플로러(Microsoft Internet Explorer), 사파리(Apple Safari), 크롬(Google Chrome), 파이어폭스(Mozilla Firefox), 오페라(Opera)

- 사용자 => 컴퓨터에 설치된 운영체제 구동 => 웹 브라우저라는 프로그램을 이용해 웹 서비스를 이용 => 웹 브라우저의 주소 창에 자신이 이용할 호스트의 웹 주소를 입력하여 접속 => 웹 서비스 받음 (포털 사이트를 이용해 정보를 찾고 정보 서비스 호스트에 접속)

- 웹 서버 환경 구성 = 아파치 + PHP + MySQL
- 맥용 웹 환경 구성 프로그램 = MAMP
- http://www.mamp.info
- vimeo.com/yamoo9/mamp


---

### 도커

[무작정 따라하는 도커](https://www.slideshare.net/pyrasis/docker-fordummies-44424016)
- 도커 이미지 = 서비스 운영에 필요한 프로그램, 소스 코드, 컴파일된 실행 파일을 묶은 형태, 저장소에 올리고 받는 것(Pull/Push)
- 도커 컨테이너 = 이미지를 실행한 상태, 이미지로 여러개의 컨테이너를 만들 수 있음. 
- 운영체제로 예를 들면 이미지는 실행파일이고 컨테이너는 프로세스.

- 도커의 이미지 수정 관리 = 유니온 파일 시스템 형식(aufs, btrfs, devicemapper)
￼
- Docker Hub 및 개인 저장소에서 이미지를 공유할 때 바뀐 부분만 주고 받음.
각 이미지는 의존 관계를 형성.

- Immutable Infrastructure 패러다임 = 호스트 os + 서비스 운영 환경(서버 프로그램, 소스 코드, 컴파일 된 바이너리)을 분리하여 한 번 설정한 운영 환경은 변경하지 않는다(Immutable)는 개념. 서비스 운영 환경을 이미지로 생성한 뒤 서버에 배포하여 실행. 서비스가 업데이트되면 운영 환경 자체를 변경하지 않고 이미지를 새로 생성하여 배포. 

- 도커 = Immutable Infrastructure를 구현한 프로젝트 = 서비스 운영 환경을 묶어 손쉽게 배포하고 실행하는 경량 컨테이너 기술

- docker <명령> 형식
    - ex) docker run, docker push
    - 항상 root 권한으로 실행













