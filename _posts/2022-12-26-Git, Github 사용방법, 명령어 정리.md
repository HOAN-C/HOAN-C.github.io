---
layout: single
title: "💾 Git, Github 사용방법, 명령어 정리"
categories:
  - github
tags: [git, github, 깃, 깃허브, 명령어, 사용방법]
comments: true
toc: true
toc_sticky: true
sidebar:
  nav: "docs"
---

💡 Git, Github 사용방법 및 명령어에 대해 알아보자!

지금까지 Git, Github를 사용하기 위한 준비를 끝냈다.

[이전 포스팅 링크](https://hoan-c.github.io/github/Git,Github-사전준비/)

이제 직접 사용해보자!

## 터미널 실행

![터미널실행](/assets/img/221226/1.png)

Git을 사용하고자 하는 프로젝트 폴더 위치로 터미널을 띄운다

## git init : git 사용시작

### git init

```
git init
```

위 명령어를 입력하면

### 실행결과

![git init](/assets/img/221226/2.png)

👏👏👏  와! 해당 프로젝트 폴더에서 git이 활성화 되었다!!

### 내부동작

![git init-inner](/assets/img/221226/3.png)

해당 폴더 내부에 _.git_ 이라는 숨김 폴더가 생성된다. 이 폴더에 변경사항, 작업등을 추적하는 기록이 남게된다.

## git add : 기록할 파일을 선택

```
git add "파일 이름" //수정된 파일 이름으로 선택
```

```
git add . //수정된 전체 파일 선택
```

직접 파일을 골라도 되고, 전체 파일을 선택해도 된다.

### 실행결과

![git add](/assets/img/221226/4.png)

다른 IDE나 에디터는 모르겠지만, VSC 기준 왼쪽 탭을 보면 “Staged Changes” 라는 공간에 우리가 작업한 파일이 들어간 것을 볼 수 있다.

### 내부동작

![git add-inner](/assets/img/221226/5.png)

지금은 작업폴더 안에 파일이 하나 이지만, 보통 프로젝트들은 방대한 파일들을 통해 작업을 진행한다.

이를 전부 기록으로 남기는것은 비효율적이므로, 수정된 파일들만을 선택하는 것이다.

### 짤막한 용어 정리

> stazing area : 수정된 파일들을 보관하는 임시 공간.

> stazing : 수정된 파일들을 고르는 작업

## git commit : 기록 명령

```
git commit -m "기록할 메시지"
```

큰따옴표 안에는 기록할 메시지를 적으면 된다. ex) “html 파일 수정”

나는 “first commit”으로 적었다.

### 실행결과

![git commit](/assets/img/221226/6.png)

🎉 git add 를 통해 추가했던 파일에 대한 기록이 완료되었다.

### 내부동작

![git commit-inner](/assets/img/221226/7.png)

git add 를 통해 선택한 파일이 저장소(repository) 에 기록되었다.

## git status : 현재상태 확인

```
git status
```

### 실행결과

![git status](/assets/img/221226/8.png)

현재 어떤 파일을 stazing 했는지, 어느 브렌치에서 작업하고 있는지 확인할 수 있다.

## git log : git 로그 확인

```
git status : 상태 확인

git log --graph --oneline --all : 해당 프로젝트 폴더내 작업내역 출력
```

위 명령어로 git 의 commit아이디 브랜치 정보등을 확인할 수 있다.

## git diff, git difftool : 이전 파일과 비교

```
git diff //이전 commit file 과 현재 파일 비교
git difftool "commitId" //현재 파일과 commitId 파일 비교(아이디 입력 안할 시 가장 최근)
```

## git branch : 프로젝트 복사, 새로운 트리 생성

```
git branch "생성할 브렌치 이름"
```

> 원본 파일을 바로 수정하면 생길 수 있는 문제를 대비하여 복사본을 만드는 것이다.

### 실행결과

![git branch](/assets/img/221226/9.png)

새로운 가지를 뻗었다!

### 브랜치 설명

브랜치(branch)는 영어로 나뭇가지를 뜻한다.

![git branc-inner](/assets/img/221226/10.png)

- 작업을 하던 프로젝트 파일 전체를 복사, 붙혀넣기 하는 것과 같은 효과를 낸다.
- 원본 브랜치를 마스터 브랜치(master branch)라고도 한다.
- 새로운 브랜치에서 어떤 작업을 하던 원본 브랜치(Master branch)에는 아무런 영향을 끼치지 않는다.
- 각 브랜치에서 각자 새로운 commit을 하며 뻗어 나갈 수 있다.

### 내부동작

git에 의해 프로젝트가 복사된다. 다만, 위 명령어로는 현 작업위치가 변경되지 않는다.

## git switch : 작업 브랜치 이동

```
git switch "이동할 브랜치 이름"
```

### 실행결과

![git switch](/assets/img/221226/11.png)

현재 브랜치가 master 에서 새로운브랜치로 이동되었다.

터미널 문구를 보면 쉽게 확인이 가능하다.

```
~/Documents/gitTest/git master
~/Documents/gitTest/git 새로운브랜치
```

### 내부동작

![git switch-inner](/assets/img/221226/12.png)

작업 위치가 새로운브랜치로 이동되었다.

### 추가설명

![git switch-exp](/assets/img/221226/13.png)

새로운브랜치에서 css파일을 추가, 기존파일 수정, commit 까지 마쳤다.

이 상태에서 원본 브랜치(master branch)로 이동한다면?

![git switch-exp](/assets/img/221226/14.png)

새로 추가한 파일은 없어지고, 기존파일을 수정한 내용도 없어졌다. (8번째 줄 참고)

이처럼 아예 다른 폴더에서 작업한 것과 같은 효과를 낸다.

## git merge : 브랜치 병합

```
git merge "병합할 브랜치 이름"
```

- 브랜치 병합은 뻗어나간 브랜치의 부모 브랜치에서 이루어져야 한다.

merge 전 git switch 를 통해 브랜치를 이동하자.

### 실행결과

![git merge](/assets/img/221226/15.png)

브랜치가 합쳐졌다!

![git log](/assets/img/221226/16.png)

```
git log --oneline --graph
```

로그 확인 구문을 입력하면 위와 같이 확인할 수 있다.

### 내부동작

![git, gitgub-merge.png](/assets/img/221226/17.png)

새로운브랜치가 원본 브랜치(Master branch)에 합쳐졌다.

## merge 고급기능

💡 3-way-merge : branch 생성 후 main branch에 새 commit이 있을 때 merge
fast-forward-merge : breanch 생성 후 main branch에 새 commit이 없을 때 merge

### rebase

```
git rebase : 3-way-merge 상황에서도 fast-forward-merge 사용 가능하게 만듦
```

### squash

```
git merge --squash "브랜치명" : log 출력시 깔끔하게 보일 수 있음
```

## git branch -d, -D : 브랜치 삭제

💡 브랜치는 merge 후에도 남아있게 된다.

```
git branch -d “branch 이름” //merge 완료된 브렌치 삭제
git branch -D “branch 이름” //merge 안한 브렌치 삭제
```

### 실행결과

![git branch-d](/assets/img/221226/18.png)

## git restore : 파일 되돌리기(단일)

```
git restore "파일명" //파일명을 최근 commit 상태로 되돌림
git restore --source "commit아이디" "파일명" //commit 시점으로 파일 복구
```

위 명령어를 입력하기 전 html 파일 속 스타일링 부분(8번째 줄) 을 지우고 새로운 commit을 만들었다.

### 실행결과

![git restore](/assets/img/221226/19.png)

명령어를 입력하니 해당 부분이 다시 생겼다.

## git revert : 이전 commit 없애기

```
git revert "commitd아이디" //commit 하나를 취소한 commit을 하나 생성
```

### 내부동작

![Untigit revert](/assets/img/221226/20.png)

## git reset : 모든 파일 되돌리기

```
git reset --hard "commit아이디" //해당 commit이 생성될 때 시점으로 전체 파일 삭제 또는 복원
git reset --soft "commit아이디" //해당 commit이 생성될 때 시점으로 파일 복원, 없는파일 staging area로
git reset --mixed "commit아이디" //해당 commit이 생성될 때 시점으로 파일 복원, 없는파일 staging 되지 않은 상태
```

- 여러명이서 협업하는 repository에서는 보통 reset 안쓴다.(갑자기 소스코드가 사라지니까)
- untracked 파일들은 (git add 안해놓은 파일들)사라지지않고 유지됨.
- git clean 명령어 사용시 untracked 파일들도 삭제 가능.

## git push : 원격저장소(github)에 업로드

💡 업로드할 원격저장소 주소가 없다면 github에서 repository(저장소) 생성 후 링크를 복사하자!

```
git push -u "원격저장주소" "브랜치명" //Github에서 만든 원격 저장소에 올리기
```

- 로컬저장소의 master 브랜치를 원격저장소에 업로드 명령어
- 브랜치명 따로 입력 안하면 모든 로컬 저장소 브랜치가 업로드 됨.
- -u 옵션은 입력 주소 기억 명령어
  - 다음부턴 git push 만 해도 동작함
- 팀원도 gitHub 아이디가 있어야 하고, push를 위해선 Collaborators에 등록되어 있어야 함.

## git clone : 원격저장소(github)에서 코드를 받아옴

```
git clone "원격저장소주소" //원격 저장소에서 코드를 받아옴
```

- 해당 링크 github repository(저장소)에 있는 코드들을 터미널을 실행한 폴더로 가져온다.

## git pull : 현재 원격 저장소 내용 가져오기

```
git pull "원격저장소주소" : 원격저장소에 있던 모든 브랜치 내용을 가져와서 로컬저장소에 합침
```

- 원격저장소에 변동사항이 생겼다면 pull 사용 후 push
- git pull 명령어는 git fetch + git merge 축약어
  - git fetch : 원격 저장소에 있는 commit 중 로컬에 없는 신규 commit 을 받아옴
  - git merge : 받아온 파일 merge.
- 팀원이 동시에 같은 파일을 수정하고 있으면 conflict 가 나니 조심.

```
git pull "원격저장소주소" : 원격저장소에 있던 모든 브랜치 내용을 가져와서 로컬저장소에 합침
```

- 원격저장소에 변동사항이 생겼다면 pull 사용 후 push
- git pull 명령어는 git fetch + git merge 축약어
  - git fetch : 원격 저장소에 있는 commit 중 로컬에 없는 신규 commit 을 받아옴
  - git merge : 받아온 파일 merge.
- 팀원이 동시에 같은 파일을 수정하고 있으면 conflict 가 나니 조심.

## git remote add : git 사용간 변수 설정

```
git remote add 변수명 저장할 값 //"변수명" 변수에 "저장할 값" 저장 명령
git remote -v //변수목록 확인
```

```
git remote add origin https://github.com/codingapple1/lesson.git
```

### 실행결과

![git remote](/assets/img/221226/21.png)
