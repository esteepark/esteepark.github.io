---
layout: post
title: "비트코인과 블럭체인 - 탐욕이 삼켜버린 기술"
excerpt: ""
categories: [dev]
date: 2018-07-19 19:30:00
comments: true
---

---
모두의 연구소 양재캠퍼스 19:30 ~ 21:30
비트코인과 블럭체인 탐욕이 삼켜버린 기술 저자 특강
---

### 비트코인: CypherPunk
*(사이퍼펑크-이걸 알아야 한다고 함)*

- 1983, E-cash:   
  - 프라이버시 보호
  - 중앙화 캐시
  - David Chaum

- 1998, B-money
  - 분산합의
  - 계산 퍼즐

- 2002, Hash cash
  - 작업증명 기반
  - Adam back

- 2005, RPOW
  - 개념에서 탈피한 첫번째 소프트웨어 구현
  - Hal Finney

- 2008, 사토시가 paper 발표

- 2009.1.3.18:05:05, 최초의 블록(제네시스블록)탄생

- 2009.1.9.02:54:25, 본격 블록 생산 시작

```
블럭 생성 보조금 21만개 블럭 발행마다 절반으로 감소
131년 동안 블록이 발행되나, 앞 24년 동안 99%의 블럭 생산, 107년동안 1%의 블럭 생산
채굴을 할 이유가 없어짐 -> 블럭체인 시장의 종말 예언
```

---

- 해시함수: SHA-256 *입력의 길이에 상관없이 항상 일정한 길이 출력*
  - 단점: 에이직? 만들기 너무 쉬움(이더리움ET어쩌고씀 -> 어려움/시간많이소요)
  - 비트코인 이후로 SHA-256은 잘 쓰지 않음
- 비대칭 암호화 기법
  - 비트코인은 블럭체인을 기반으로 구성
  - 모든 트랜젝션을 모든 노드가 공유
- 작업증명
  - 작업증명을 해야하는 유일한 이유 = 수익창출(돈)
  - 수익창출이 없다면 작업증명을 해야 할 이유가 없음
  - Incentive Engineering

---

- 용어정리
  - 분산 vs 탈웅앙화
    - 이 두가지를 구분해서 사용해야 함
    - 일이 분산되면 분산시스템
    - 일을 분산하고 특정 노드가 개입되어도 일이 분산되면 분산시스템
    - 특정 노드가 특정 역할을 할 경우 => 성능 향상 -> 중앙화 시스템 장점
    - 절대 익명성 문제를 상업적으로 사용할 때 풀어야 하는지 화두

  - 중앙화 시스템 = 신뢰 기반 거래: 거래 내역을 신뢰할 것인가?
  - 탈중앙화 시스템 = 증명 기반 거래: 규칙을 지켰는가?
    - 리더(기록자)선출 -> 기록 -> 검증 ->
        - 동의 -> 합의 -> 반복 or 기각 -> 반복
        - 10분 간격으로 이를 반복(시스템마다 반복 시간 다름)

  - 브로드캐스팅: Gossip protocol: 거래처리방식
    - 트랜잭션 처리단계1
      - 트랜잭션작성 -> peer전파를 통한 브로드캐스팅 -> 각 노드 대기열에서 대기
      - 각 노드는 다른 노드의 상태를 알지 못하고 peer에 대한 정보변경 감지
      - 처리하는 데이터는 1개, 처리하는 사람은 매번 변경
    - 트랜젝션 처리단계2
      - 블록만들기(해시퍼즐풀기)경쟁 -> 블록 완성한 노드가 브로드캐스팅 -> 모든 노드가 블록 검증(블럭의 해시코드 검증)
    - 트랜젝션 처리단계3
      - 정상적 블록일 경우 기존 블록체인에 추가
      - 비정상적 블록일 경우 즉시 폐기
      - 블록체인은 비동기화 시스템 => 블록이 동시에 생성되었을 경우 탈중앙화 합의 규칙 적용
        - 탈중앙화 합의 규칙  

          ```
          블록 동시 생성되었을 경우
          각 노드는 타 노드의 상태 모름
          자신의 블럭에 대한 검증 진행
          같은 블럭체인 위에 서로 다른 블럭체인 생성
          어느순간 peer를 통해 서로의 블럭체인이 다르다는 것을 감지
          둘 다 규칙을 지켰지만 내용이 다름
          블럭체인은 항상 하나의 상태만 가져야하기 때문에 둘 중에 하나는 폐기시켜야 함
          둘 중에 더 긴 놈을 살림

          <그래서, 탈중앙화 함의 규칙>
          1. 규칙을 어긴 놈 퇴출
          2. 규칙을 지켰지만 긴 놈을 살림

          블럭에 시그니처가 있음 -> 채굴자 확인 가능
          동시에 같은 블록이 다가왔을때 적용할 블럭을 선택할 수 있음

          ```
  - 블록체인
    - 블록체인은 블록의 체인이다.
    - 블록은 거래내역을 기록하고 거래가 일어난 순서대로 저장되어 있지 않음. (수수료가 제일 많은 놈부터 처리)
    - 블록은 거래내역을 기록하고 저장된 순서대로 거래가 일어난 것임. (이중사용의 문제)
    - 1. 비트코인의 소유자가 맞는지 확인    2. 사용하려는 돈이 쓸려는 돈보다 많은지 적은지 확인
    - 항상 블록을 거꾸로 타고 올라가서 확인
    - 비트코인 블록체인 = 블라인드 블록체인
      - 특정 블록체인으로는 확인 불가 -> 사용하기 전에 블록체인의 히스토리를 다 뒤져서 확인해봐야함

  - UTXO(Unspent Transaction Output)
    - 누가 출력한 것인데 내가 아직 쓰지 않고 있다면 그게 비트코인(?) -> 이것이 UTXO
    - 비트코인은 누군가에게 받은 것 -> 그 누군가도 누군가에게 받은 것 -> 도대체 누가 최초 발행하는 거? 의문
      - 모든 블록의 첫번째는 코인베이스
      - 코인베이스가 발행되고 코인베이스를 쓰기 시작하면 트랜젝션 발생
      - 코인베이스가 만들어진 것은 내 뒤에 100개의 블럭이 생겨야(?) 사용 가능(코인베이스 생성 후 약 하루 사용 불가)

  - TPS(Transactions per seconds)
    - 처리건수/용량 -> 블럭체인이 풀어야할 가장 큰 문제
    - 블럭체인에 음악/영상을 올리겠다는 말은 불가능

  - 중계 / 중개 / 중재
    - 중개인이 들어가 있는 모든 시스템에 블럭체인을 적용 기대
    - if 비밀번호를 잃어버리는 순간 -> 중개인이 없기 때문에 그냥 사용할 수 없음
    - if 기계가 손상될 경우 -> 복구 불가
    - 비트코인을 가장 안전하게 저장할 수 있는 방법 = 종이(8개의 seed를 적어서 안전한 곳에 보관)

  - 이중 사용
    - 비동기 시스템으로 인해 발생 가능한 문제 = 이중 사용
    - 상대방이 블럭이 도착할 때까지 기다리면 가능하나 상거래입장에서 보면 적용 불가능한 거래 조건

  - 블록과 숫자
    - 블록의 높이: 고정, 항상 같음
    - 블록의 깊이: 변경, 깊이가 6정도되면 안전하다고 할 수 있음, 6이하는 퇴출 가능성 있음
    - 블록의 해시함수

  - 소프트 포크 vs 하드 포크
    - 하나의 기능을 변경했을때, 소속된 2000만명의 시스템을 모두 변경해야 함
    - 하드포크: 과거에는 무효하던 규칙을 유효화한 경우(모든 노드가 업그레이드 하지 않으면 합의되지 않는 것)
    - 소프트포크: 과거에는 유효하던 규칙을 무효화한 경우(모든 노드가 업그레이드 하지 않아도 강제로 따라가는 것)
    - 하드포크와 소프트포크의 공통점: 새로운 규칙을 따르는 노드가 앞질러야 함
      - 채굴업자가 키를 쥐고 있음 = 마이너 엑비베이트
      - 채굴업자가 업그레이드하면 그 규칙을 따르게 됨
      - 현재는 채굴업자가 돈을 잘벌고 있으니 어뷰징하지 않지만, 가능성 존재
        - 채굴업자에 의해 프로그램이 장악될 가능성
        - 시스템을 장악하면 이중사용을 할 수 있음
        - 선의의 해시파워가 악의를 가진 해시파워보다 강해야 한다.

  - 작업증명
    - 나쁜짓을 못하게 하기 위해 돈이 들게 하는 시스템
    - 작업증명의 비대칭성
      - 작업증명은 엄청난 자원이 필요하면서 정확성 검증은 매우 간단해야 함

  - 블록체인의 비가역성
    - 하나가 바뀌면 그 뒤가 모두 바뀌며 미리 계산해 둘 수 없음

  - 머클트리
    - 어디를 바꾸던지 루트를 변경하지 않고서는 바뀌지 않음

  - 비트코인 블록체인의 문제점
    - 작업증명 -> 몇개의 노드가 독점하는 현상 발생
    - 블라인드 블록체인
    - 범용성의 부재
      - 새로운 용도는 소스 코드 자체를 수정해야 함
    - 기타
      - 10분의 하나씩 생산 -> 용량 제한
    이런 문제를 해결하겠다고 나온 것이 이더리움
    - 이더리움 계약(contract)의 역할
      - 데이터 저장소 관리
      - 전달계약: 복잡한 조건을 처리할 수 있는 EOA
      - 계약의 관리
      - 소프트웨어 라이브러리 역할 - 다른 계약에 기능을 제공

    - 스마트계약
      - 조건부 이체 (예: 축구 우승팀 맞추기)
      - 제 3자의 개입없이도 계약 체결 가능

    - General purpose blockchain

    - ICO (Initial Coin Offering): IPO를 빗대어 만든 신조어

    - IPO (Initial Public Offering)

    블록체인의 효용
      - 해킹으로부터의 안정성유지보수비용 점감
      - 중간자 없는 거래
      - 비가역적 불변성을 요하는 기록(쓰고나면 비가역적으로 되나 쓰기 전에는 아님)
      - 성능 느림, 진실만 기록되는지 모름

    MainNet의 구성
      - 안정적 참여자로 구성된 네트워크를 구축할 수 있나?
      - 메인넷이 없다면 하이브리드로 가야 함
      - 메인넷 필수조건
        - 충분한 참여자
        - 지속적 참여
        - 지역적 분포
        - 자융적 운영

    기존 MainNet 활용

    비잔틴 장군 문제
      - 신뢰할 수 없는 통신
      - 악의적 행동도 가능

    ```
    블럭체인 비트코인 10분에 1개씩 생산
    term이 길면 길수록 퇴출될 가능성 줄어들며 term이 짧을수록 퇴출 가능성이 높음
    ```


---

블럭체인의 데이터 저장 -> 모든 시스템 참여자가 블록체인을 개별적으로 저장 -> 어디를 해킹할 것인가 ?

노드 두종류 있음
  - 모든 모드는 80byte의 헤더를 가지고 있음 -> 풀노드(?)

현재 블럭체인의 92%를 10개 업체가 채굴 => 전세계를 10개의 은행이 장악한 것과 동일



---
