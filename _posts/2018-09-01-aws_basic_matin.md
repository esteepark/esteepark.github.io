---
layout: post
title: "aws basic with Matin Hwang"
excerpt: ""
categories: [dev]
date: 2018-09-01 20:00:00
comments: true
---

1. 계정 로그인
2. 인스턴스 : EC2 를 생성(인스턴스 시작)
3. 단계1: Amazon Machine Image(AMI)선택 - 우분투 서버 16.04 LTS (HVM), SSD Volume Type - ami - 00
4. 단계2: 인스턴스 유형 선택 - t2.micro 유형 (프리 티어 사용 가능)
5. 단계3: 인스턴스 세부 정보 구성 - 디폴트로 '다음: 스토리지 추가'
6. 단계4: 스토리지 추가 - 크가(GiB)를 30으로 변경
7. 단계5: 태그 추가 - 디폴트로 '다음: 보안 그룹 구성:
8. 단계6: 보안 그룹 구성 - 포트 개방 범위 설정
9. 단계7: 인스턴스 시작 검토 - 설정 내용 검토 후 시작
10. 키페어 선택 및 선택 후 인스턴스 생성하고 약 1-2분 후 인스턴스 생성
11. 생성된 인스턴스를 클릭하면 하단의 설명에 IPv4 퍼블릭 IP, 퍼블릭 DNS(IPv4)를 이용해 서버에 접근 가능
12. ssh -i *estee.pem:::pem 보안키를 넣는다 보안키는 절대 경로로 넣어주는 것이 좋다 ~/Desktop/estee.pem* ubuntu@*13.125.250.182:::DNS 혹은 IPv4 퍼블릭 IP를 넣는다*
13. 터미널을 열고 아래를 순차적으로 입력 ssh -i estee.pem ubuntu@13.125.251.51 yes sudo apt-get install language-pack-ko sudo apt-get update sudo apt-get install nginx 
14. nginx 상태 확인 및 실행 명령어 sudo service nginx status #엔진엑스 상태확인 sudo service nginx start #엔진엑스 시작 sudo service nginx stop #엔진엑스 중지 sudo service nginx restart #엔진엑스 재시작 
15. 만약 pem 으로 접속이 안되면 ls -l 로 권한정보를 확인하고 rw-r-r 로 되어 있다면 권한을 바꿔줘야 한다. rw- - - 로 권한 변경은 sudo chmod 600 estee.pem 
16. 네트워크 및 보안 탭의 탄력적 IP(엘라스틱 IP)를 들어가 '새 주소 할당'을 선택해 새 주소를 할당한다
17. 할당된 주소를 오른쪽 클릭해 '주소 연결'을 선택한다. 적용할 인스턴스를 선택하고 어소시에이트 ! #그럼 이제 IP가 고정 되었음! 인스터스를 중지했다가 다시 시작해도 IP가 변경되지 않음 #엘라스틱IP를 적용해주면 우분투 연결이 끊어짐 다시 해줘야함 #근데 이렇게 해도 브라우저에서 IP를 쳐서 들어갈 때 제대로 들어가지 않을 수 있음 80포트를 열어줘야함
18. 포트열기 네트워크 및 보안 탭에 보안 그룹에 들어가서 '보안 그룹 생성' 선택(인스턴스 상태를 보고 인스턴스에 적용되어 있는 보안 그룹의 인바운드를 변경해주어야 함) 인바운드 - 유형: HTTP - 프로토콜: TCP - 포트범위: 80 - 소스: 위치무관(어느 공유기의 IP에 접속해 있어도 서버에 접근 할 수 있음)

[AWS 언제나 무료](https://aws.amazon.com/ko/free/?awsf.Free%20Tier%20Types=categories%23alwaysfree)
