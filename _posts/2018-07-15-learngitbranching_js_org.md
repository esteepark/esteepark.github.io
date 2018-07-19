---
layout: post
title: "Learn git branchin"
excerpt: ""
categories: [paragraph]
date: 2018-07-15 00:00:00
comments: true
---


main
====

### git 기본

-	커밋 소개: `git commit`

> ```
> - 디렉토리의 모든 파일에 대한 스냅샷을 기록하는 것
> - 디렉토리 전체를 복붙하는 것과 비슷하나 훨씬 유용
> - 커밋을 가볍게 유지하기 위해 커밋할 때마다 디렉토리 전체를 복사하지 않음
> - 각 커밋은 저장소의 이전 버전과 다음 버전의 변경내역(delta)을 저장
> - 그래서 대부분의 커밋이 부모 커밋을 가르킴
>
> git commit    # HEAD 위치에서 새로운 커밋을 하나 생성
> ```

-	브랜치 쓰기: `git branch newImage`

> ```
> - 깃의 브랜치는 놀랍도록 가벼움
> - 브랜치는 특정 커밋에 대한 참조 reference 에 지나지 않음
> - 깃 예찬론자 어록: '브랜치를 서둘러, 자주 만들어라'
> - 브랜치를 많이 만들어도 메모리, 디스크 공간에 부담없음
> - 커다란 하나의 브랜치 < 작은 단위의 여러개의 브랜치
> - 브랜치 간단 정리 = 하나의 커밋과 그 부모 커밋드를 포함하는 작업 내역
>
> git branch master2    # 현재 커밋 위에 git-test 브랜치 생성
> ```

-	브랜치 합치기: `git merge`

> ```
> - 브랜치끼리의 작업을 접목하는 첫번째 방법
> - 머지는 두 개의 부모를 가리키는 특별한 커밋을 만듬
> - 두개의 부모가 있는 커밋 = 두 부모의 모든 작업내역 + 두 부모의 모든 부모들의 작업내역
> - HEAD 위치에서 지정한 브랜치를 합치며 새로운 커밋 생성
> - HEAD가 커밋 위에 있다면 HEAD 혼자 놀러다님
> - HEAD가 브랜치 위에 있다면 두 브랜치를 합침   
>
> git merge master    # 현재 HEAD가 위치한 브랜치가 master 브랜치를 가르키며 새로운 커밋 생성
> ```

-	리베이스의 기본: `git rebase`

> ```zsh
> - 브랜치끼리의 작업을 접목하는 두번째 방법
> - 리베이스 = 커밋들을 모아서 복사한 뒤, 다른 곳에 떨궈 놓는 것
> - 커밋들의 흐름을 보기 좋게 한 줄로 만들 수 있음
> - 저장소의 커밋 로그와 이력이 매우 깨끗해짐
>
> git rebase master    # HEAD가 위치한 브랜치가 master 브랜치 위로 복사되어 한 줄의 트리로 커밋 정리
> git checkout master; git rebase bugFix    # master 브랜치에 bugFix 브랜치를 병합
> ```

### 다음 단계로

-	HEAD 분리하기

> ```
> - HEAD = 현재 체크아웃된 커밋 = 현재 작업중인 커밋 = 항상 작업트리의 최큰 커밋
> - 작업트리에 변화를 주는 git 명령어들은 대부분 HEAD를 변경하는 것으로 시작
> - 일반적으로 HEAD는 브랜치의 이름을 가르킴 -> if 커밋 -> 브랜치 상태변경 -> 변경내용 HEAD를 통해 확인 가능
>
> git checkout C1; git checkout master; git commit; git checkout C2
> # if master -> C1, HEAD가 C1 커밋 가르킴 (헤드분리: HEAD -> C1, master -> C1);
>   HEAD가 master 브랜치 가르킴 (HEAD -> master -> C1);
>   새로운 커밋 생성 (HEAD -> master -> C2);
>   HEAD가 C2 커밋 가르킴 (헤드분리: HEASD -> C2, master -> C2)
> ```

-	상대 참조(^) (Relative Refs)

> ```
> - git log = 해시 확인 명령어
> - 해시 = 커밋의 고유 값(ex: fed2da64c0efc5293610bdda8792740d38dg2789dke9)
> - 상대참조 = 기억하는 지점부터 원하는 지점으로 이동하도록 작업 가능
> - ^(캐럿) = 한번에 한 커밋 위로 움직이는 상대 커밋
> -
>
> git checkout master^    # master 브랜치의 부모 커밋으로 HEAD 이동
> git checkout HEAD^    # 현재 HEAD의 부모 커밋으로 HEAD 이동
> ```

-	상대 참조(~)

  >```
  > - ~(틸드)<num> = 한번에 num 만큼의 커밋 위로 올라가는 상대 커밋
  > 
  > git checkout HEAD~4    # 현재 HEAD의 4번째 전 커밋으로 이동
  > git branch -f master HEAD~3    # 현재 HEAD의 3번째 전 커밋으로 master 브랜치 이동
  >```

-	작업 되돌리기
> ```
> - 낮은 수준의 일(개별 파일이나 묶음을 스테이징 하는 것)과 높은 수준의 일(실제 변경이 복구되는 방법) 있음
> - reset = 애초에 커밋하지 않은 것처럼 예전 커밋으로 브랜치를 옮기는 것, 
>           브랜치가 예전의 커밋을 가리키도록 이동 
> - revert = 변경분을 되돌리고 되돌린 내용을 사람들에게 공유하기 위해서는 revert를 사용해야 함, 
>            히스토리를 고쳐쓴다는 점 때문에 다른 사람이 작업하는 리모트 브랜치에는 reset을 사용할 수 없음
>
> git reset HEAD~1    # 현재 HEAD의 부모 커밋으로 이동하며 현재 HEAD가 위치했던 커밋은 없었던 것과 마찬가지인 상태가 됨
> git revert HEAD    # 현재 HEAD의 부모 커밋으로 이동 후 커밋을 복사해 다시 커밋한다(트리의 모양 유지)
> ```

### 코드 이리저리 옮기기

-	cherry-pick 소개

-	인터렉티브 리베이스 소개

### 종합선물세트

-	딱 한개의 커밋만 가져오기

-	커밋들 갖고 놀기

-	커밋들 갖고 놀기2

-	태그

-	묘사

### 고급 문제

-	9천번이 넘는 리베이스

-	다수의 부모

-	브렌치 스파게티

---

remote
======

### push & pull -- 원격 저장소

-	clone 소개

-	원격 브랜치(remote branch)

-	git fetch

-	git pull

-	가짜 팀워크

-	git push

-	엇갈린 히스토리

### origin 그 너머로 -- 고급 원격 저장소

-	push master

-	원격 작업과 merge 하기

-	원격 저장소 추적하기

-	git push의 인자들

-	git push 인자 -- 확장판!

-	fetch의 인자들

-	source가 없다

-	pull 인자들
